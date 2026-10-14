---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Family member and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: family-member, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product removes the Family member with the Profile and each Wallet access
  kind: product
  actor: owner
  entities:
  - {entity: family-member, effect: removes, from: Active}
  - {entity: profile, effect: removes, with: family-member}
  - {entity: wallet-access, effect: removes, with: family-member}
  contexts:
    r:
      place: web::administration::family-members
---

# Remove a member

## Trigger

The owner deletes a member and confirms.

## Outcome

The member, their profile and every wallet access they held are gone; transactions they recorded stay.

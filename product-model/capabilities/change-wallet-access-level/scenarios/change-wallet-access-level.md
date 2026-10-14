---
kind: primary
routes:
  r: Web
steps:
- text: The Owner switches the Wallet access between View and Manage and saves
  kind: actor
  actor: owner
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product keeps the new level
  kind: product
  actor: owner
  entities:
  - {entity: wallet-access, effect: changes, facts: [Level]}
  contexts:
    r:
      place: web::administration::family-members
---

# Change an access level

## Trigger

The owner changes an account from View to Manage for a member, or back, and saves.

## Outcome

The member's abilities on that account follow the new level at once.

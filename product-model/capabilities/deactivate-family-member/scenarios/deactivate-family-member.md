---
kind: primary
routes:
  r: Web
steps:
- text: The Owner switches the Family member off
  kind: actor
  actor: owner
  entities:
  - {entity: family-member, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product marks the Family member inactive and ends every session
  kind: product
  actor: owner
  entities:
  - {entity: family-member, effect: changes, from: Active, to: Inactive, facts: []}
  contexts:
    r:
      place: web::administration::family-members
---

# Deactivate a member

## Trigger

The owner switches a member's Active switch off.

## Outcome

The member is inactive, signed out everywhere at once and refused at sign-in.

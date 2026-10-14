---
kind: primary
routes:
  r: Web
steps:
- text: The Owner switches the Family member back on
  kind: actor
  actor: owner
  entities:
  - {entity: family-member, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product marks the Family member active
  kind: product
  actor: owner
  entities:
  - {entity: family-member, effect: changes, from: Inactive, to: Active, facts: []}
  contexts:
    r:
      place: web::administration::family-members
---

# Reactivate a member

## Trigger

The owner switches an inactive member's Active switch on.

## Outcome

The member can sign in again with the same password and access.

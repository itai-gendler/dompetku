---
kind: validation
routes:
  r: Web
steps:
- text: The Owner enters a username that is already used
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::family-members
- text: The Product refuses the new member
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: reads, facts: [Username]}
  contexts:
    r:
      place: web::administration::family-members
---

# The username is taken

## Trigger

The owner picks a username already in use, or the owner's own.

## Outcome

No member is added and the owner is told the username is taken.

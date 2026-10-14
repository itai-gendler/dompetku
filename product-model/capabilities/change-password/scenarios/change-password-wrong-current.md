---
kind: validation
routes:
  r: Web
steps:
- text: The Family member enters a wrong current password
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app::profile
- text: The Product refuses without changing the password
  kind: product
  actor: family-member
  entities:
  - {entity: profile, effect: reads, facts: [Password]}
  contexts:
    r:
      place: web::app::profile
---

# The current password is wrong

## Trigger

A family member mistypes the current password.

## Outcome

Nothing changes and the member is told the current password is wrong.

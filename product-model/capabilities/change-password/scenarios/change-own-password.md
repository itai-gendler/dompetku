---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the current password and a new one
  kind: actor
  actor: owner
  entities:
  - {entity: profile, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::profile
- text: The Product checks the current password and the rules for the new one, stores it and ends every other session
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: changes, facts: [Password]}
  contexts:
    r:
      place: web::app::profile
---

# Change one's own password

## Trigger

The owner wants a new password.

## Outcome

The new password replaces the configured one for good and every other session is signed out.

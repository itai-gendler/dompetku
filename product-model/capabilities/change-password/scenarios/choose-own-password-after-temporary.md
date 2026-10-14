---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member enters the temporary password and a new one
  kind: actor
  actor: family-member
  entities:
  - {entity: family-member, effect: reads, facts: [Must change password]}
  contexts:
    r:
      place: web::app::profile
- text: The Product stores the new password and clears the need to change it
  kind: product
  actor: family-member
  entities:
  - {entity: profile, effect: changes, facts: [Password]}
  - {entity: family-member, effect: changes, facts: [Must change password]}
  contexts:
    r:
      place: web::app::profile
---

# Choose one's own password after a temporary one

## Trigger

A family member signed in with a temporary password.

## Outcome

The member's own password replaces the temporary one and the rest of the app opens.

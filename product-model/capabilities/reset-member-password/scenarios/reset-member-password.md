---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters a new temporary password for the Family member
  kind: actor
  actor: owner
  entities:
  - {entity: family-member, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product stores it, requires a change at next sign-in and ends every session of the member
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: changes, facts: [Password]}
  - {entity: family-member, effect: changes, facts: [Must change password]}
  contexts:
    r:
      place: web::administration::family-members
---

# Reset a member's password

## Trigger

A member forgot their password.

## Outcome

The member is signed out everywhere and must change the new temporary password at next sign-in.

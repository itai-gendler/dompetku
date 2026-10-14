---
kind: primary
result: achieved
routes:
  r: Web
steps:
- text: The Family member signs in with the temporary password
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::public::sign-in
  capability: sign-in
- text: The Product opens the session and sends the Family member to change the password
  kind: product
  actor: family-member
  entities:
  - {entity: family-member, effect: reads, facts: [Must change password]}
  contexts:
    r:
      place: web::public::sign-in
  capability: sign-in
- text: The Family member enters the temporary password and a new one
  kind: actor
  actor: family-member
  entities:
  - {entity: family-member, effect: reads, facts: [Must change password]}
  contexts:
    r:
      place: web::app::profile
  capability: change-password
- text: The Product stores the new password and clears the need to change it
  kind: product
  actor: family-member
  entities:
  - {entity: profile, effect: changes, facts: [Password]}
  - {entity: family-member, effect: changes, facts: [Must change password]}
  contexts:
    r:
      place: web::app::profile
  capability: change-password
---

# A member replaces the temporary password

## Trigger

The owner added the member, or reset their password, and the member signs in for the first time since.

## Outcome

The member's own password is in place and every page the member may open is reachable.

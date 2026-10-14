---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member enters their username and the temporary password
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::public::sign-in
- text: The Family member must still change the password
  kind: condition
  actor: family-member
  entities:
  - {entity: family-member, effect: reads, facts: [Must change password]}
  contexts:
    r:
      place: web::public::sign-in
- text: The Product opens the session and sends the Family member to change the password
  kind: product
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::public::sign-in
---

# A family member signs in with a temporary password

## Trigger

A family member signs in with the temporary password the owner gave them.

## Outcome

The member is signed in but held on their profile page until they choose their own password.

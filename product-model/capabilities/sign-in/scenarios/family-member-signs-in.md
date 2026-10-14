---
kind: primary
routes:
  r: Web
steps:
- text: The Family member enters their username and password
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::public::sign-in
- text: The Family member is active and the password matches
  kind: condition
  actor: family-member
  entities:
  - {entity: family-member, effect: reads, facts: []}
  - {entity: profile, effect: reads, facts: [Username, Password]}
  contexts:
    r:
      place: web::public::sign-in
- text: The Product opens a session for the Family member
  kind: product
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::public::sign-in
---

# A family member signs in

## Trigger

A family member opens the sign-in page.

## Outcome

The member is signed in with their own password and lands in the app; two-step sign-in never applies to members.

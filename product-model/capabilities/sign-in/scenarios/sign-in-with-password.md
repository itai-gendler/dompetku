---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the username and password
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::public::sign-in
- text: The Product checks the password against the one stored for that username, or the configured one when none is stored
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: reads, facts: [Username, Password]}
  contexts:
    r:
      place: web::public::sign-in
- text: The session opens and the Owner is in the app
  kind: condition
  actor: owner
  entities: []
  contexts:
    r:
      place: web::public::sign-in
---

# Sign in with a password

## Trigger

The owner opens the sign-in page while two-step sign-in is off.

## Outcome

A session valid for seven days is open and the owner is in the app.

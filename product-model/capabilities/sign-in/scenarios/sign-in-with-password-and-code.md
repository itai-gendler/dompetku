---
kind: alternative
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
- text: The Product checks the password and asks for a six-digit code, valid for five minutes
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: reads, facts: [Username, Password]}
  contexts:
    r:
      place: web::public::sign-in
- text: The Owner enters the code from the authenticator app
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::public::sign-in
- text: The code matches and the session opens
  kind: condition
  actor: owner
  entities: []
  contexts:
    r:
      place: web::public::sign-in
---

# Sign in with a password and a code

## Trigger

The owner opens the sign-in page while two-step sign-in is on.

## Outcome

A session valid for seven days is open after both steps; a wrong or late code opens nothing.

## Edge cases

- A code entered after five minutes asks the owner to start again from the password.

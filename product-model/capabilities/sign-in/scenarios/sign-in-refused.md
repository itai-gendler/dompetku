---
kind: validation
routes:
  r: Web
steps:
- text: The Owner enters a wrong password
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::public::sign-in
- text: The Product refuses after a short delay
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: reads, facts: [Password]}
  contexts:
    r:
      place: web::public::sign-in
---

# Sign-in is refused

## Trigger

Someone enters a wrong username, password or code.

## Outcome

Nothing opens and the answer comes after a short delay.

## Edge cases

- An inactive or removed family member is refused like a wrong password.

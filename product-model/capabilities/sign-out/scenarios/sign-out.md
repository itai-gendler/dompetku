---
kind: primary
routes:
  r: Web
steps:
- text: The Family member chooses Log out
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app
- text: The Product ends the session on this device
  kind: product
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app
---

# Sign out

## Trigger

A signed-in person chooses Log out.

## Outcome

The session on this device ends and the sign-in page is shown.

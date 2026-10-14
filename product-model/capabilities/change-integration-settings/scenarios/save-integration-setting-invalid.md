---
kind: validation
routes:
  r: Web
steps:
- text: The Owner enters an n8n API key that is too short
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::integrations
- text: The Product refuses the value
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::integrations
---

# A value is invalid

## Trigger

The n8n API key is shorter than 24 characters, or another value fails its check.

## Outcome

Nothing is saved and the owner is told why.

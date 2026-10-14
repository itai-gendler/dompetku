---
kind: validation
routes:
  r: Web
steps:
- text: The Owner uploads a logo larger than 200 KB
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::app-settings
- text: The Product refuses the settings
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::app-settings
---

# A setting is invalid

## Trigger

The logo is over 200 KB or not PNG, JPEG or WebP, the time zone is unknown or the GitHub link is not https.

## Outcome

Nothing is saved and the owner is told which value is wrong.

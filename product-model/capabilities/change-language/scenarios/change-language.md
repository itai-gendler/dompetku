---
kind: primary
routes:
  r: Web
steps:
- text: The Family member switches the language
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app
- text: The Product shows the app in that language and remembers it on this device
  kind: product
  actor: family-member
  entities:
  - {entity: device-preferences, effect: changes, facts: [Language]}
  contexts:
    r:
      place: web::app
---

# Switch the language

## Trigger

A family member switches the app to English.

## Outcome

Every page is shown in English on this device from now on.

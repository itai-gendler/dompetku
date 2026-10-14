---
kind: primary
routes:
  r: Web
steps:
- text: The Family member taps the eye button
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app
- text: The Product hides every amount on this device and remembers it
  kind: product
  actor: family-member
  entities:
  - {entity: device-preferences, effect: changes, facts: [Privacy mode]}
  contexts:
    r:
      place: web::app
---

# Hide amounts on this device

## Trigger

A family member is about to share their screen.

## Outcome

Amounts are hidden on this device until shown again, also after reloading.

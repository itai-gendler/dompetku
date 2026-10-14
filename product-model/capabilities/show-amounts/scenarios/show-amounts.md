---
kind: primary
routes:
  r: Web
steps:
- text: The Family member taps the eye button again
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app
- text: The Product shows amounts again on this device
  kind: product
  actor: family-member
  entities:
  - {entity: device-preferences, effect: changes, facts: [Privacy mode]}
  contexts:
    r:
      place: web::app
---

# Show amounts again

## Trigger

Amounts are hidden and the person taps the eye button again.

## Outcome

Amounts are shown again on this device.

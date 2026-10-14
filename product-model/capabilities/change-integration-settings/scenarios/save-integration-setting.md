---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters a value and saves
  kind: actor
  actor: owner
  entities:
  - {entity: integration-settings, effect: reads, facts: [Allowed chat IDs]}
  contexts:
    r:
      place: web::administration::integrations
- text: The Product checks the value, encrypts secrets and keeps it
  kind: product
  actor: owner
  entities:
  - {entity: integration-settings, effect: changes, facts: [Allowed chat IDs]}
  contexts:
    r:
      place: web::administration::integrations
---

# Save an integration setting

## Trigger

The owner enters the allowed chat IDs and saves.

## Outcome

The value applies within about a minute and the screen shows it comes from the app.

---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner removes a saved value
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::integrations
- text: The Product forgets the saved value
  kind: product
  actor: owner
  entities:
  - {entity: integration-settings, effect: changes, facts: [AI key]}
  contexts:
    r:
      place: web::administration::integrations
---

# Remove a saved value

## Trigger

The owner removes the saved AI key.

## Outcome

The deployment's value, or the default, applies again.

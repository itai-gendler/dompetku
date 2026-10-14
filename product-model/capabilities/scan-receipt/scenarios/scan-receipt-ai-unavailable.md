---
kind: edge
routes:
  r: Web
steps:
- text: The Owner scans a receipt
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The language model is not configured or fails
  kind: condition
  actor: owner
  entities:
  - {entity: integration-settings, effect: reads, facts: [AI endpoint, AI key]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product shows the reason and leaves the form empty
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
---

# The AI cannot read the receipt

## Trigger

No AI key is set, the provider refuses or its credit is used up.

## Outcome

The owner is told why and fills the form by hand.

## Edge cases

- On a demo instance scanning is turned off.

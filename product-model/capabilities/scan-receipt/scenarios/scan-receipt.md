---
kind: primary
routes:
  r: Web
steps:
- text: The Owner takes or picks a receipt photo
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Product asks the language model to read the receipt and fills the form with existing category names
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
---

# Fill the form from a receipt photo

## Trigger

The owner scans a receipt while recording.

## Outcome

The form is filled with what the receipt shows; the owner checks it and saves or discards it.

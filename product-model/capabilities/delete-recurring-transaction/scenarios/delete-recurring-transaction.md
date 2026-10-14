---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Recurring transaction and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product removes it
  kind: product
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: removes, from: Active}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# Delete a schedule

## Trigger

The owner deletes a recurring transaction and confirms.

## Outcome

Nothing more is posted; transactions already posted remain.

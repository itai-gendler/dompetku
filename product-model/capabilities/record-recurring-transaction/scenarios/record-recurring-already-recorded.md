---
kind: edge
routes:
  r: Web
steps:
- text: The Owner taps Record now again
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::recurring-transactions
- text: A Transaction for that occurrence exists
  kind: condition
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Notes]}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product moves the next due date on without recording again
  kind: product
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# The occurrence was already recorded

## Trigger

The occurrence due was recorded before, for example by a second tap.

## Outcome

No second transaction is made; the schedule still moves on and the owner is told it was recorded before.

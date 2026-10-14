---
kind: primary
routes:
  r: Web
steps:
- text: The Owner pauses the Recurring transaction
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product marks it paused
  kind: product
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: changes, from: Active, to: Paused, facts: []}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# Pause a schedule

## Trigger

The owner taps Pause.

## Outcome

Nothing comes due while it is paused.

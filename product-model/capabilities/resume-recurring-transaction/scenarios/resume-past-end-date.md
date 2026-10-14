---
kind: validation
routes:
  r: Web
steps:
- text: The Owner resumes a Recurring transaction whose end date has passed
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: [End date]}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product refuses
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::recurring-transactions
---

# A schedule past its end date cannot resume

## Trigger

The owner resumes a schedule whose next occurrence would fall after its end date.

## Outcome

It stays paused and the owner is told the schedule has passed its end date.

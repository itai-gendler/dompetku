---
kind: primary
routes:
  r: Web
steps:
- text: The Owner resumes the Recurring transaction
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product moves the next due date to the first occurrence on or after today and marks it active
  kind: product
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: changes, from: Paused, to: Active, facts: [Next due date]}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# Resume a schedule

## Trigger

The owner taps Resume.

## Outcome

The schedule is active again with its next due date on or after today; nothing missed is posted.

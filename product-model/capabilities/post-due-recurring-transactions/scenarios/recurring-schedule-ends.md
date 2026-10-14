---
kind: edge
routes:
  r: Web
steps:
- text: The next occurrence of a Recurring transaction falls after its end date
  kind: condition
  unattended: true
  entities:
  - {entity: recurring-transaction, effect: reads, facts: [End date, Next due date]}
  contexts:
    r:
      place: web::app
- text: The Product marks the Recurring transaction paused
  kind: product
  entities:
  - {entity: recurring-transaction, effect: changes, from: Active, to: Paused, facts: [Next due date]}
  contexts:
    r:
      place: web::app
---

# A schedule reaches its end date

## Trigger

The next occurrence of an automatic schedule would fall after its end date.

## Outcome

The schedule is paused and nothing after the end date is posted.

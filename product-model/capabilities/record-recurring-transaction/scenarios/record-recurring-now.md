---
kind: primary
routes:
  r: Web
steps:
- text: The Owner taps Record now on a Recurring transaction
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: [Name, Next due date]}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product records the occurrence as a Transaction and moves the next due date on
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Source]}
  - {entity: recurring-transaction, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# Record the current occurrence

## Trigger

The owner taps Record now on a schedule.

## Outcome

The occurrence due is recorded as a transaction dated today and the schedule moves to its next date.

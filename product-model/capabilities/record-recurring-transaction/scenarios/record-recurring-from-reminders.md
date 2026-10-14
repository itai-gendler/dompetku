---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner taps Record on a due Recurring transaction
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: [Name, Amount, Next due date]}
  contexts:
    r:
      place: web::app::reminders
- text: The Product records the occurrence and moves the next due date on
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Source]}
  - {entity: recurring-transaction, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: web::app::reminders
---

# Record a manual item from Reminders

## Trigger

A manual recurring item is due and the owner taps Record in Reminders.

## Outcome

The occurrence is recorded and disappears from the reminders until the next one is near.

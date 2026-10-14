---
kind: primary
routes:
  r: Web
steps:
- text: The dashboard, the reminders or a bot report is needed while an active automatic Recurring transaction is due
  kind: condition
  unattended: true
  entities:
  - {entity: recurring-transaction, effect: reads, facts: [Auto-post, Next due date, End date]}
  contexts:
    r:
      place: web::app
- text: The Product records each due occurrence not yet recorded as a Transaction dated on its due day and moves the next due date on
  kind: product
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Source]}
  - {entity: recurring-transaction, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: web::app
---

# Post due occurrences

## Trigger

The owner's dashboard, the reminders or a bot report is needed while automatic occurrences are due.

## Outcome

Each due occurrence exists once as a transaction on its due date and each schedule shows its next date.

## Edge cases

- When more than 12 occurrences are missed, only the latest 12 are posted and the older ones are skipped.
- Manual schedules are never posted; they appear in Reminders instead.

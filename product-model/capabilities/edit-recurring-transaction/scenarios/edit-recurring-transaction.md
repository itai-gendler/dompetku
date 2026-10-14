---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Recurring transaction
  kind: actor
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: reads, facts: [Name, Amount, Cycle, Next due date]}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: changes, facts: [Name, Kind, Amount, Currency, Cycle, Interval, Day of month, Start date, Next due date, End date, Auto-post, Description, Merchant]}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# Edit a schedule

## Trigger

The owner edits a recurring transaction.

## Outcome

Future occurrences follow the new schedule; posted ones stay as they are.

---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the name, kind, amount, accounts, category, cycle, interval, day, start and end, and whether to post automatically
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product works out the first due date and keeps the active Recurring transaction
  kind: product
  actor: owner
  entities:
  - {entity: recurring-transaction, effect: creates, to: Active, facts: [Name, Kind, Amount, Currency, Cycle, Interval, Day of month, Start date, Next due date, End date, Auto-post, Description, Merchant]}
  contexts:
    r:
      place: web::app::recurring-transactions
---

# Schedule a recurring transaction

## Trigger

The owner adds salary on the 25th of every month.

## Outcome

The schedule is active with its first due date on or after the start date.

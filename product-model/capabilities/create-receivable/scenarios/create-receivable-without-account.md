---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner enters a loan without an account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::receivables
- text: The Product keeps the active Receivable
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: creates, to: Active, facts: [Purpose, Borrower, Amount, Currency, Lent date, Due date, Notes]}
  contexts:
    r:
      place: web::app::receivables
---

# Record money lent without an account

## Trigger

The owner records a loan without choosing an account.

## Outcome

The receivable is active; no transaction is recorded.

---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the purpose, borrower, amount, dates and the Account it came from
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::receivables
- text: The Product keeps the active Receivable and, with it, the expense in Piutang
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: creates, to: Active, facts: [Purpose, Borrower, Amount, Currency, Lent date, Due date, Notes]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Notes, Source], with: receivable}
  contexts:
    r:
      place: web::app::receivables
---

# Record money lent from an account

## Trigger

The owner lends 1 million from BCA to a friend.

## Outcome

The receivable is active with the whole amount remaining, and the account shows the loan as an expense.

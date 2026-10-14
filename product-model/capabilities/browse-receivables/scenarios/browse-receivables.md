---
kind: primary
routes:
  r: Web
steps:
- text: The Owner reads each Receivable and Receivable payment
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: [Purpose, Borrower, Amount, Currency, Lent date, Due date, Paid, Remaining]}
  - {entity: receivable-payment, effect: reads, facts: [Amount, Paid date]}
  contexts:
    r:
      place: web::app::receivables
---

# See receivables

## Trigger

The owner opens Receivables.

## Outcome

Each receivable shows lent, paid and remaining amounts, the due date and its payments.

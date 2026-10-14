---
kind: primary
routes:
  r: Web
steps:
- text: The Owner taps Pay on the Debt
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date, Remaining amount]}
  contexts:
    r:
      place: web::app::debts
- text: The Product records the expense and the Installment payment with the next number
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source], with: installment-payment}
  - {entity: installment-payment, effect: creates, facts: [Installment number, Amount, Paid date]}
  contexts:
    r:
      place: web::app::debts
---

# Pay an installment

## Trigger

The owner taps Pay on a debt.

## Outcome

The next installment is paid, the expense is recorded and the next due date moves to the following month.

---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner taps Pay on a Debt with one installment left
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Remaining amount]}
  contexts:
    r:
      place: web::app::debts
- text: The Product records the expense and the last Installment payment and marks the Debt paid off
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source], with: installment-payment}
  - {entity: installment-payment, effect: creates, facts: [Installment number, Amount, Paid date]}
  - {entity: debt, effect: changes, from: Active, to: Paid off, facts: []}
  contexts:
    r:
      place: web::app::debts
---

# Pay the last installment

## Trigger

The owner pays the final installment.

## Outcome

The debt is paid off and no longer listed as due.

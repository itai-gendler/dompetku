---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner deletes an Installment payment of a paid-off Debt
  kind: actor
  actor: owner
  entities:
  - {entity: installment-payment, effect: reads, facts: [Installment number, Amount, Paid date]}
  - {entity: debt, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::debts
- text: The Product removes the Installment payment with its Transaction and marks the Debt active
  kind: product
  actor: owner
  entities:
  - {entity: installment-payment, effect: removes}
  - {entity: transaction, effect: removes, with: installment-payment}
  - {entity: debt, effect: changes, from: Paid off, to: Active, facts: []}
  contexts:
    r:
      place: web::app::debts
---

# Reopen a paid-off debt

## Trigger

The owner removes a payment from a paid-off debt.

## Outcome

The payment and its expense are gone and the debt is active again with one installment due.

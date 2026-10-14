---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes an Installment payment from the Debt's history
  kind: actor
  actor: owner
  entities:
  - {entity: installment-payment, effect: reads, facts: [Installment number, Amount, Paid date]}
  - {entity: debt, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::debts
- text: The Product removes the Installment payment with its Transaction
  kind: product
  actor: owner
  entities:
  - {entity: installment-payment, effect: removes}
  - {entity: transaction, effect: removes, with: installment-payment}
  contexts:
    r:
      place: web::app::debts
---

# Delete an installment payment

## Trigger

The owner removes a payment from an active debt's history.

## Outcome

The payment and its expense are gone and the installment counts as unpaid again.

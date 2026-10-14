---
kind: validation
routes:
  r: Web
steps:
- text: The Owner tries to pay a Debt with no installment left
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Remaining amount]}
  contexts:
    r:
      place: web::app::debts
- text: The Product refuses
  kind: product
  actor: owner
  entities:
  - {entity: installment-payment, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::debts
---

# A paid-off debt takes no more payments

## Trigger

Every installment of the debt is already paid.

## Outcome

Nothing is recorded and the owner is told the debt is paid off.

---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Debt and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::debts
- text: The Product removes the Debt and each Installment payment
  kind: product
  actor: owner
  entities:
  - {entity: debt, effect: removes, from: Active}
  - {entity: installment-payment, effect: removes, with: debt}
  contexts:
    r:
      place: web::app::debts
---

# Delete a debt

## Trigger

The owner deletes a debt and confirms.

## Outcome

The debt and its installment payments are gone.

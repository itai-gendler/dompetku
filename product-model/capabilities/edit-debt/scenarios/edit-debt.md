---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Debt
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Number of installments]}
  contexts:
    r:
      place: web::app::debts
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: debt, effect: changes, facts: [Name, Provider, Kind, Currency, Total amount, Installment amount, Number of installments, First installment month, Due day, Interest rate, Notes]}
  contexts:
    r:
      place: web::app::debts
---

# Edit a debt

## Trigger

The owner edits a debt.

## Outcome

The remaining amount and next due date follow the new values.

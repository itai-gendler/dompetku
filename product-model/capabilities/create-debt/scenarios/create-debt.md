---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the debt's name, provider, kind, amounts, installments, first month and due day
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::debts
- text: The Product keeps the active Debt
  kind: product
  actor: owner
  entities:
  - {entity: debt, effect: creates, to: Active, facts: [Name, Provider, Kind, Currency, Total amount, Installment amount, Number of installments, First installment month, Due day, Interest rate, Notes]}
  contexts:
    r:
      place: web::app::debts
---

# Add a debt

## Trigger

The owner adds a paylater purchase.

## Outcome

The debt is active with its first installment due in the first installment month.

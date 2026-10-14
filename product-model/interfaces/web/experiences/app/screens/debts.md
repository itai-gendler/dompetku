---
entities:
- {entity: debt, shows: [Name, Provider, Kind, Installment amount, Number of installments, Next due date, Remaining amount], collects: [Name, Provider, Kind, Currency, Total amount, Installment amount, Number of installments, First installment month, Due day, Interest rate, Notes]}
- {entity: installment-payment, shows: [Installment number, Amount, Paid date]}
entryPoints:
- web: /debts
references:
- kind: code
  role: implementation
  target: src/routes/_app/debts.tsx
---

# Debts & installments

Debts with paid and remaining installments, next due date and the payment history.

---
entities:
- {entity: debt, shows: [Name, Installment amount, Next due date]}
- {entity: subscription, shows: [Name, Amount, Next due date]}
- {entity: recurring-transaction, shows: [Name, Amount, Next due date]}
- {entity: account, shows: [Name, Monthly fee, Monthly fee day]}
- {entity: budget, shows: [Spent this month]}
entryPoints:
- web: /reminders
references:
- kind: code
  role: implementation
  target: src/routes/_app/reminders.tsx
---

# Reminders

Bills due in the next 7, 30 or 90 days — installments, subscriptions, manual recurring items, monthly account fees — and budgets past their warning, with Pay or Record on each bill.

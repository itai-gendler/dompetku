---
entities:
- {entity: recurring-transaction, shows: [Name, Kind, Amount, Currency, Cycle, Interval, Next due date, End date, Auto-post], collects: [Name, Kind, Amount, Currency, Cycle, Interval, Day of month, Start date, Next due date, End date, Auto-post, Description, Merchant]}
- {entity: account, shows: [Name]}
- {entity: category, shows: [Name]}
entryPoints:
- web: /recurring
references:
- kind: code
  role: implementation
  target: src/routes/_app/recurring.tsx
---

# Recurring transactions

Recurring incomes, expenses and transfers with their next due date, automatic or manual, and the monthly totals.

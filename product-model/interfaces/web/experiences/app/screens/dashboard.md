---
entities:
- {entity: account, shows: [Name, Balance]}
- {entity: transaction, shows: [Kind, Amount in IDR, Date, Description]}
- {entity: category, shows: [Name]}
- {entity: pocket, shows: [Name, Remaining, Low-balance threshold]}
entryPoints:
- web: /dashboard
references:
- kind: code
  role: implementation
  target: src/routes/_app/dashboard.tsx
---

# Dashboard

The month at a glance: balances, net worth, cash flow, spending per category, upcoming bills and pockets running low. A family member's dashboard covers only their accounts.

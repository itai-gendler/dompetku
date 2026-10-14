---
entities:
- {entity: account, shows: [Name, Balance, Currency]}
- {entity: pocket, shows: [Name, Allocated amount, Low-balance threshold, Period, Archived, Remaining], collects: [Name, Allocated amount, Low-balance threshold, Period, Archived]}
- {entity: transaction, shows: [Kind, Amount, Date, Description]}
- {entity: category, shows: [Name]}
- {entity: reconciliation, shows: [As-of date, Statement balance, App balance, Difference], collects: [As-of date, Statement balance]}
entryPoints:
- web: /accounts/:id
references:
- kind: code
  role: implementation
  target: src/routes/_app/accounts_.$id.tsx
- kind: code
  role: implementation
  target: src/components/account-pockets.tsx
- kind: code
  role: implementation
  target: src/components/account-reconcile.tsx
---

# Account detail

One account: its 12-month balance, spending per category and its pockets with what is left this month and what is unallocated.

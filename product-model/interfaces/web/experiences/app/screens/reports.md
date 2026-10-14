---
entities:
- {entity: transaction, shows: [Amount in IDR, Date]}
- {entity: category, shows: [Name]}
- {entity: account, shows: [Name]}
entryPoints:
- web: /reports
references:
- kind: code
  role: implementation
  target: src/routes/_app/reports.tsx
---

# Reports

Spending per category over 6 or 12 months and month totals, for all accounts or one.

---
entities:
- {entity: budget, shows: [Monthly limit, Alert percent, Rollover, Spent this month, Carried amount, Effective limit], collects: [Monthly limit, Alert percent, Rollover]}
- {entity: category, shows: [Name]}
entryPoints:
- web: /budgets
references:
- kind: code
  role: implementation
  target: src/routes/_app/budgets.tsx
---

# Budgets

This month's budgets: limit, carried amount, effective limit, what is spent and left, and where the warning is.

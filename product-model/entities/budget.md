---
domain: budgets
references:
- kind: code
  role: implementation
  target: src/lib/budget.ts
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeBudgets
---

# Budget

A monthly spending limit for one expense category.

## Information kept

- **Monthly limit** — the limit per month in IDR
- **Alert percent** — the share of the limit at which a warning is given, 80 by default
- **Rollover** — when on, what is left of each month (or the overspend) carries into the next, looking back at most 12 months
- **Spent this month** — expenses in the category this month, in IDR
- **Carried amount** — the remainder or overspend carried in from earlier months
- **Effective limit** — monthly limit plus carried amount

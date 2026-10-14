---
appliesTo:
- {type: capability, id: view-dashboard}
- {type: capability, id: view-reports}
- {type: capability, id: view-yearly-recap}
- {type: entity, id: transaction, facts: [Amount in IDR]}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#getUsdIdr
---

# Totals are computed in IDR

Every amount is kept in IDR or USD with its IDR equivalent at the day's rate; balances, budgets, reports and net worth add up in IDR, and the base currency only changes how amounts are displayed.

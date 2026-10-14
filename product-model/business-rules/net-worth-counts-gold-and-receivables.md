---
appliesTo:
- {type: capability, id: view-dashboard}
- {type: entity, id: account, facts: [Balance]}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#netWorthSeries
---

# Net worth counts gold and outstanding receivables

The owner's net worth is account balances plus gold at today's buyback price plus what borrowers still owe; the cash spent on gold or lent out is counted once.

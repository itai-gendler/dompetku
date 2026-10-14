---
appliesTo:
- {type: capability, id: record-transaction}
- {type: capability, id: accept-transaction-preview}
- {type: entity, id: budget}
references:
- kind: code
  role: implementation
  target: src/lib/budget.server.ts#budgetAlertsFor
- kind: code
  role: implementation
  target: src/lib/budget.ts#crossedLevels
---

# Each budget warns at most once per level per month

A budget's warning level (its alert percent) and its limit each warn at most once per calendar month, the first time spending crosses them.

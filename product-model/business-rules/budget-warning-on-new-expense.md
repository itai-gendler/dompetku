---
appliesTo:
- {type: capability, id: record-transaction}
- {type: capability, id: accept-transaction-preview}
- {type: entity, id: budget}
references:
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#saveTransaction
- kind: code
  role: implementation
  target: src/lib/budget.server.ts#budgetAlertsFor
---

# A new expense dated this month can give a budget warning

When the owner saves a new expense on the web, or a bot preview is saved, and it is dated in the current month, the save reports each budget level it crosses. Family members never get budget warnings, since budgets are the owner's.

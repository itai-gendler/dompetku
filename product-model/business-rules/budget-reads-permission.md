---
appliesTo:
- {type: entity, id: budget, effect: reads}
permits:
- actors: [owner]
- actors: [n8n-automation]
references:
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#saveTransaction
---

# Only the owner sees budgets

Budgets are the owner's; the owner's n8n workflows read them for reminders. Family members never see budgets or budget warnings.

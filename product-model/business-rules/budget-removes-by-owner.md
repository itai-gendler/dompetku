---
appliesTo:
- {type: entity, id: budget, effect: removes}
permits:
- actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/server-fn-access.ts#SERVER_FN_ACCESS
- kind: code
  role: implementation
  target: src/lib/permissions.ts#can
---

# Only the owner removes budgets

Only the owner removes budgets; family members cannot, and the Telegram bot acts for the owner.

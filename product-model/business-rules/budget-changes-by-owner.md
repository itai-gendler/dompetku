---
appliesTo:
- {type: entity, id: budget, effect: changes}
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

# Only the owner changes budgets

Only the owner changes budgets; family members cannot, and the Telegram bot acts for the owner.

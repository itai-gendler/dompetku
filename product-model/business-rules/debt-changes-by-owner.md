---
appliesTo:
- {type: entity, id: debt, effect: changes}
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

# Only the owner changes debts

Only the owner changes debts; family members cannot, and the Telegram bot acts for the owner.

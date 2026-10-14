---
appliesTo:
- {type: entity, id: debt, effect: creates}
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

# Only the owner creates debts

Only the owner creates debts; family members cannot, and the Telegram bot acts for the owner.

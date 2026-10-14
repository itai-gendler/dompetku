---
appliesTo:
- {type: entity, id: recurring-transaction, effect: removes}
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

# Only the owner removes recurring transactions

Only the owner removes recurring transactions; family members cannot, and the Telegram bot acts for the owner.

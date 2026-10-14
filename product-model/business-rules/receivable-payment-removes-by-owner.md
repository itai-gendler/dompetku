---
appliesTo:
- {type: entity, id: receivable-payment, effect: removes}
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

# Only the owner removes receivable payments

Only the owner removes receivable payments; family members cannot, and the Telegram bot acts for the owner.

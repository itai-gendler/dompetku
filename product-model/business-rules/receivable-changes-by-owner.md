---
appliesTo:
- {type: entity, id: receivable, effect: changes}
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

# Only the owner changes receivables

Only the owner changes receivables; family members cannot, and the Telegram bot acts for the owner.

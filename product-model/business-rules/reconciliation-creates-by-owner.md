---
appliesTo:
- {type: entity, id: reconciliation, effect: creates}
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

# Only the owner creates reconciliations

Only the owner creates reconciliations; family members cannot, and the Telegram bot acts for the owner.

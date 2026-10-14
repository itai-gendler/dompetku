---
appliesTo:
- {type: entity, id: wallet-access, effect: removes}
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

# Only the owner removes wallet access

Only the owner removes wallet access; family members cannot, and the Telegram bot acts for the owner.

---
appliesTo:
- {type: entity, id: account, effect: changes}
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

# Only the owner changes accounts

Only the owner changes accounts; family members cannot, and the Telegram bot acts for the owner.

---
appliesTo:
- {type: entity, id: subscription, effect: changes}
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

# Only the owner changes subscriptions

Only the owner changes subscriptions; family members cannot, and the Telegram bot acts for the owner.

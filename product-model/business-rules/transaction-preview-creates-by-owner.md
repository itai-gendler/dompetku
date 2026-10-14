---
appliesTo:
- {type: entity, id: transaction-preview, effect: creates}
permits:
- actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#chatAllowed
- kind: code
  role: implementation
  target: src/lib/permissions.ts#ADMIN_MODULES
---

# Only the owner creates transaction previews

Only the owner creates transaction previews; family members cannot, and the Telegram bot acts for the owner.

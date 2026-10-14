---
appliesTo:
- {type: context, context: {place: telegram-bot}}
- {type: entity, id: integration-settings, facts: [Allowed chat IDs]}
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#chatAllowed
- kind: code
  role: implementation
  target: src/lib/integrations.ts#isChatAllowed
---

# The bot answers only allowed chats

The bot serves only chats among the allowed chat IDs, and an empty list refuses every chat, before any finance data is read.

---
type: messaging
actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#handleBotUpdate
- kind: code
  role: implementation
  target: src/routes/api/public/n8n/bot.ts
- kind: code
  role: implementation
  target: src/routes/api/public/telegram/webhook.ts
- kind: doc
  role: intent
  target: docs/N8N.md
  title: Telegram bot guide
---

# Telegram bot

The owner's own Telegram bot, answering private chats and allowed groups. Updates reach the app
either through the owner's n8n workflow or directly through a Telegram webhook; both give the
same replies. In a group the bot answers only messages that mention it, reply to it or use one of
its commands. Replies are in Indonesian.

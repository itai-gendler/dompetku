---
availability:
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#undoTransaction
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#undoLast
---

# Undo bot transaction

Remove a transaction the bot saved: with the Undo button within 7 days of saving, or with /undo for the latest bot transaction of the last 24 hours. Its fee goes too, and receipt photos no other transaction uses.

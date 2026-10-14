---
availability:
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#handleBotUpdate
- kind: code
  role: implementation
  target: src/lib/bot.ts#quickParse
- kind: code
  role: implementation
  target: src/lib/bot-group.ts#groupAddress
- kind: code
  role: implementation
  target: src/lib/ai-usage.server.ts#botAiQuotaReached
---

# Create transaction preview

Turn a chat message or a receipt photo into a preview with buttons. Short messages such as "kopi 25rb" or "gaji masuk 8jt ke BCA" are read without AI, the category guessed from the words or from earlier transactions with the same description. Other messages, and receipts, are read by the configured language model, snapped onto existing categories and accounts.

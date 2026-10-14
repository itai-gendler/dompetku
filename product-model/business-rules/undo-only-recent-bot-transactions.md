---
appliesTo:
- {type: capability, id: undo-bot-transaction}
- {type: entity, id: transaction, effect: removes}
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#undoTransaction
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#isBotTransaction
---

# Undo removes only recent bot transactions

Undo removes only a transaction the bot recorded: the Undo button within 7 days of saving, /undo the latest one within 24 hours. It never removes the other parts of a split.

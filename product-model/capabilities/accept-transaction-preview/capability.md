---
availability:
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#createFromExternal
- kind: code
  role: implementation
  target: src/lib/budget.server.ts#budgetAlertsFor
---

# Accept transaction preview

Tap Save on a preview to record it as a transaction — with the bot's default account when none was named and in the tagged pocket when the account has one of that name — and get an Undo button. Saving twice records once.

---
availability:
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts
- kind: code
  role: implementation
  target: src/lib/bot.ts#pickEditTarget
---

# Edit transaction preview

Correct a waiting preview from its buttons: pick another category or account, switch between income and expense, or tap Keterangan and send the new description (up to 200 characters) as the next message within 10 minutes.

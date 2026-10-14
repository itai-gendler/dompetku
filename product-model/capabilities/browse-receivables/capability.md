---
domain: receivables
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#listReceivables
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#receivablesText
---

# Browse receivables

See money lent, what each borrower still owes, due dates and payments, with the IDR total outstanding. The bot's /piutang lists the active ones with what is left.

---
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#payDebt
---

# Pay installment

Record the next installment of a debt as paid: an expense of the installment amount in Cicilan & Hutang from the debt's account, and the payment in its history. Paying the last one marks the debt paid off. Reached from Debts, Reminders and the bot's /bayar, which records at once without a preview.

---
domain: transactions
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#listTransactions
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#listText
---

# Browse transactions

Find transactions by month, kind, category, account or pocket, search descriptions, merchants and receipt item names, sort and page through them. A family member sees transactions touching their accounts, with any other account shown as Other wallet. The bot lists a period's incomes or expenses.

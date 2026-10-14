---
domain: budgets
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeBudgets
- kind: code
  role: implementation
  target: src/lib/budget.ts#rolloverCarry
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#budgetText
---

# Browse budgets

See, for one month, each budget's limit, carried amount, effective limit, spending and what is left or overspent. The bot's /budget shows this month's use with a bar per category.

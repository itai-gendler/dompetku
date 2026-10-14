---
domain: accounts
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#getBalances
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#balancesText
---

# Browse accounts

See accounts and their balances. A family member sees only the accounts shared with them; the bot's /saldo lists every unarchived account with an IDR total.

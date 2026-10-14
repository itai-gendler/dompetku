---
availability:
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#cashWithdraw
---

# Withdraw cash

Record an ATM withdrawal from the bot with "/tarik 500rb dari BCA": a transfer from the named account (else the first bank account) into the first cash account, which is created as Tunai when none exists. It records at once, without a preview.

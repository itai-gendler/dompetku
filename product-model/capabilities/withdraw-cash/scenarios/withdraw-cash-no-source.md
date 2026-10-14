---
kind: validation
routes:
  r: Telegram
steps:
- text: The Owner sends /tarik without an amount
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product asks for the amount and records nothing
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# No account to withdraw from

## Trigger

No account is named and no bank account exists, or no amount is given.

## Outcome

Nothing is recorded and the bot asks for the account or the amount.

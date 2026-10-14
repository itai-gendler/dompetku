---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /kantong
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with every Pocket and its remaining amount, grouped by Account
  kind: product
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: [Name, Remaining, Allocated amount]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for pockets

## Trigger

The owner sends /kantong.

## Outcome

The bot lists every account's pockets with what is left this month.

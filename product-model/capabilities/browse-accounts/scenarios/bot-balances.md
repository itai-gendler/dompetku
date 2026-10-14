---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /saldo
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with each unarchived Account balance and the IDR total
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Type, Currency, Balance, Archived]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for balances

## Trigger

The owner sends /saldo.

## Outcome

The bot lists every unarchived account's balance and the total in IDR at today's USD rate.

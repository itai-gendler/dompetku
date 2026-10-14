---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /tagihan
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: No number of days is given, so the reminder days from App settings apply, else 14
  kind: condition
  actor: owner
  entities:
  - {entity: app-settings, effect: reads, facts: [Reminder days]}
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with each bill and budget warning in the window
  kind: product
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date]}
  - {entity: subscription, effect: reads, facts: [Name, Amount, Next due date]}
  - {entity: budget, effect: reads, facts: [Spent this month]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for bills

## Trigger

The owner sends /tagihan, optionally with a number of days up to 90.

## Outcome

The bot lists the bills of the window, or says there are none.

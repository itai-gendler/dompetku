---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /piutang
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with each active Receivable and its remaining amount
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: [Purpose, Borrower, Remaining, Due date]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for receivables

## Trigger

The owner sends /piutang.

## Outcome

The bot lists every active receivable with what is left and its due date.

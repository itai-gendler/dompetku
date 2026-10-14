---
kind: validation
routes:
  r: Telegram
steps:
- text: The Owner taps Undo on an old confirmation
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Transaction is older than 7 days
  kind: condition
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Source]}
  contexts:
    r:
      place: telegram-bot
- text: The Product refuses and points to the web app
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# Undo is refused

## Trigger

The transaction is older than 7 days, was not made by the bot, or the button belongs to no preview of this chat.

## Outcome

Nothing is removed and the bot says to delete it on the web.

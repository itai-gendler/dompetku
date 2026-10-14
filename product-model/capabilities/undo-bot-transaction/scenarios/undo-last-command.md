---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /undo
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: A bot Transaction was saved in the last 24 hours
  kind: condition
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Source]}
  contexts:
    r:
      place: telegram-bot
- text: The Product removes the latest one and marks its preview undone
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: removes}
  - {entity: transaction-preview, effect: changes, from: Accepted, to: Undone, facts: []}
  contexts:
    r:
      place: telegram-bot
---

# Undo the latest with /undo

## Trigger

The owner sends /undo.

## Outcome

The latest bot transaction is removed when it was saved within the last 24 hours.

## Edge cases

- With no bot transaction in the last 24 hours the bot says so and removes nothing.

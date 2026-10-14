---
kind: validation
routes:
  r: Telegram
steps:
- text: The Owner writes to the bot from a chat not yet allowed
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The chat is not among the allowed chat IDs
  kind: condition
  actor: owner
  entities:
  - {entity: integration-settings, effect: reads, facts: [Allowed chat IDs]}
  contexts:
    r:
      place: telegram-bot
- text: The Product replies that the bot is not configured for this chat ID
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# The chat is not allowed

## Trigger

A message arrives from a chat that is not among the allowed chat IDs, or none are set.

## Outcome

The bot reads no finance data, keeps nothing and replies with the chat ID to add.

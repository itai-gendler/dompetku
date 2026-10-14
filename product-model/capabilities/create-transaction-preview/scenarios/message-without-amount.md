---
kind: validation
routes:
  r: Telegram
steps:
- text: The Owner sends a message without an amount
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with examples and keeps nothing
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# No amount can be read

## Trigger

The owner sends a message with no amount, or longer than 300 characters for AI.

## Outcome

No preview is kept; the bot shows examples, or asks for a shorter message.

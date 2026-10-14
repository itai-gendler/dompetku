---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner writes in the group without mentioning the bot
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product sends nothing
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# A group message not addressed to the bot

## Trigger

Someone writes in an allowed group without mentioning the bot, replying to it or using a command.

## Outcome

The bot stays silent and uses no AI.

## Edge cases

- A mention of the bot is stripped before the message is read.

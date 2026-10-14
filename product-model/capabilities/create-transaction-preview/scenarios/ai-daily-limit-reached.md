---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner sends a receipt photo
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The chat has reached its daily AI limit
  kind: condition
  actor: owner
  entities:
  - {entity: integration-settings, effect: reads, facts: [Daily AI limit per chat]}
  contexts:
    r:
      place: telegram-bot
- text: The Product replies that the AI quota is used up
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# The chat's daily AI limit is used up

## Trigger

The chat has used its daily AI calls and the message or photo needs AI.

## Outcome

No preview is kept; the bot suggests the short format and says photos work again tomorrow.

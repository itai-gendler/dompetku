---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner's message is delivered a second time
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: A Transaction preview exists for that chat and update
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
- text: The Product sends the existing preview again
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# The same message arrives twice

## Trigger

Telegram or n8n delivers the same update again.

## Outcome

The bot answers with the same preview; no second preview is made.

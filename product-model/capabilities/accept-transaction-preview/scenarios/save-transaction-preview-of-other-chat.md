---
kind: validation
routes:
  r: Telegram
steps:
- text: The Owner's tap names a preview of another chat
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product answers that the preview was not found
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Chat]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# A button from another chat

## Trigger

A Save tap names a preview made in another chat.

## Outcome

Nothing is recorded and the bot says the preview was not found.

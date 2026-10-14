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
- text: The language model is not configured or fails
  kind: condition
  actor: owner
  entities:
  - {entity: integration-settings, effect: reads, facts: [AI endpoint, AI key, Receipt model]}
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with a warning giving the reason
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
---

# The AI cannot read the message

## Trigger

No AI key is configured, or the provider fails or runs out of credit.

## Outcome

No preview is kept and the bot replies with the reason.

---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner taps Batal just after Save
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Transaction preview is no longer waiting
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product answers that the preview was already handled
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# The preview was already handled

## Trigger

Cancel is tapped on a preview that a racing Save already recorded.

## Outcome

The saved transaction and its photo stay; the message says the preview was already handled.

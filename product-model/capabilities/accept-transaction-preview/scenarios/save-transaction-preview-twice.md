---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner taps Save on a preview already saved
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Transaction preview is already saved
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product answers that it was saved before
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Save is tapped twice

## Trigger

The owner taps Save again, or the tap is delivered twice.

## Outcome

No second transaction is made; the message says it was already saved, still with Undo.

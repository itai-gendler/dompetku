---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner taps Save on an old preview
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The preview is older than 48 hours
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product closes the preview without recording
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, from: Proposed, to: Dismissed, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# The preview has expired

## Trigger

The owner taps Save more than 48 hours after the preview was made.

## Outcome

Nothing is recorded; the preview is closed and the owner is asked to send the transaction again.

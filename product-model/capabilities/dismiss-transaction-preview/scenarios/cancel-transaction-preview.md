---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner taps Batal on the preview
  kind: actor
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Amount, Description]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product closes the preview and deletes its receipt photo
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, from: Proposed, to: Dismissed, facts: [Receipt photo]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Cancel a preview

## Trigger

The owner taps Cancel.

## Outcome

Nothing is recorded, the receipt photo is deleted and the message says so.

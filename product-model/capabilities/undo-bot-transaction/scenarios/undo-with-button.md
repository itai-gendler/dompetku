---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner taps Undo
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Transaction was saved from a preview of this chat less than 7 days ago
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Chat]}
  - {entity: transaction, effect: reads, facts: [Source]}
  contexts:
    r:
      place: telegram-bot
- text: The Product removes the Transaction and marks the preview undone
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: removes}
  - {entity: transaction-preview, effect: changes, from: Accepted, to: Undone, facts: []}
  contexts:
    r:
      place: telegram-bot
---

# Undo with the button

## Trigger

The owner taps Undo under a saved confirmation.

## Outcome

The transaction is removed, the preview is marked undone and the bot names what was removed.

---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner sends a short message with an amount
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product reads kind, amount, currency, account and date, guesses an existing category, and keeps the preview
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: transaction-preview, effect: creates, to: Proposed, facts: [Chat, Kind, Amount, Currency, Category, Account, Date, Description, Merchant, Receipt items, Read by]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
- text: The preview shows what was read and that it was read without AI
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Kind, Amount, Category, Account, Date, Description, Read by]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Preview a short message

## Trigger

The owner sends "kopi 25rb".

## Outcome

A preview read without AI waits in the chat with Save, Cancel and edit buttons.

## Decision points

### Chat AI mode

How is the Chat AI mode in Integration settings set?

- auto or not set → the message is read without AI when it can be, else by AI
- never → only the reading without AI is tried
- always → the message goes to AI even when it could be read without it

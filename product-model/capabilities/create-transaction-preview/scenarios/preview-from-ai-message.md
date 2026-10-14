---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends a longer message with an amount
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The chat is under its daily AI limit
  kind: condition
  actor: owner
  entities:
  - {entity: integration-settings, effect: reads, facts: [Daily AI limit per chat, Chat AI mode]}
  contexts:
    r:
      place: telegram-bot
- text: The Product asks the language model to read it, snaps the result onto an existing Category and account, and keeps the preview
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: transaction-preview, effect: creates, to: Proposed, facts: [Chat, Kind, Amount, Currency, Category, Account, Date, Description, Merchant, Receipt items, Read by]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
---

# Preview a message read by AI

## Trigger

The owner sends a message the quick reading cannot handle, with an amount in it and at most 300 characters.

## Outcome

A preview read by AI waits in the chat, marked to be checked before saving.

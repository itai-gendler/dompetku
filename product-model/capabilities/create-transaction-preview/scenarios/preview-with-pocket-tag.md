---
kind: alternative
routes:
  r: Telegram
steps:
- text: 'The Owner sends a message ending in a #tag'
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product reads the message, keeps the tag and keeps the preview
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: creates, to: Proposed, facts: [Chat, Kind, Amount, Currency, Category, Account, Date, Description, Merchant, Receipt items, Read by, Pocket tag]}
  contexts:
    r:
      place: telegram-bot
---

# Preview a message with a pocket tag

## Trigger

The owner sends "kopi 25rb #makan".

## Outcome

The preview carries the pocket tag; on saving it lands in that pocket of the account when one has that name.

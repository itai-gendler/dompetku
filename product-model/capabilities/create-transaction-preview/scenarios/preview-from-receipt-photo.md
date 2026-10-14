---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends a receipt photo with the caption "pakai BCA"
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product has the language model read the receipt, takes the account from the caption, stores the photo and keeps the preview
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: transaction-preview, effect: creates, to: Proposed, facts: [Chat, Kind, Amount, Currency, Category, Account, Date, Description, Merchant, Receipt items, Read by, Receipt photo]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
---

# Preview a receipt photo

## Trigger

The owner sends a receipt photo, optionally with a caption naming the account.

## Outcome

A receipt preview with merchant and up to 50 items waits in the chat; the photo is kept privately with it.

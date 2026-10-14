---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner taps Save on the preview
  kind: actor
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Kind, Amount, Currency, Category, Account, Date, Description]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The preview is still waiting and less than 48 hours old
  kind: condition
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product records the Transaction from the preview, using the default account from App settings when none was named, and marks the preview saved
  kind: product
  actor: owner
  entities:
  - {entity: app-settings, effect: reads, facts: [Bot default account]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Receipt items, Receipt photos, Source]}
  - {entity: transaction-preview, effect: changes, from: Proposed, to: Accepted, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The confirmation shows Undo and each budget or pocket level crossed for the first time this month
  kind: condition
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: [Spent this month, Effective limit]}
  - {entity: pocket, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Save a preview

## Trigger

The owner taps Save.

## Outcome

The transaction is recorded; the message turns into a saved confirmation with Undo and any budget or pocket warning crossed.

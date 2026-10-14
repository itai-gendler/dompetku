---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner taps Masuk/Keluar
  kind: actor
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Kind, Category]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product flips the kind and matches the category to the other kind
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name, Kind]}
  - {entity: transaction-preview, effect: changes, facts: [Kind, Category]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Switch income and expense

## Trigger

The owner taps Masuk/Keluar.

## Outcome

The preview flips kind and keeps the category when one of that name exists for the other kind, else uses Lainnya.

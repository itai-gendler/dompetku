---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner taps Kategori and picks a Category from the list
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: transaction-preview, effect: reads, facts: [Kind, Category]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product updates the preview
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, facts: [Category]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Pick another category

## Trigger

The owner taps Kategori on a preview.

## Outcome

The preview shows the chosen category.

---
kind: primary
routes:
  r: Web
steps:
- text: The Owner picks a CSV file and checks the preview
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Product skips rows already recorded and saves the others, matching categories and accounts by name
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name, Kind]}
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Source]}
  contexts:
    r:
      place: web::app::transactions
---

# Import a CSV file

## Trigger

The owner picks a CSV file on the Transactions page and confirms the preview.

## Outcome

Each valid, new row is saved as an imported transaction and the owner sees how many were imported and skipped.

## Edge cases

- A row with the same date, type, amount, currency and description as a recorded transaction, or as an earlier row of the file, is skipped as a duplicate.

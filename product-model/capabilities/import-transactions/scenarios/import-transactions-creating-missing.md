---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner ticks Create missing and confirms
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Product creates each missing Category and Account named in the file
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: creates, facts: [Name, Kind]}
  - {entity: account, effect: creates, facts: [Name, Type, Currency]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product saves each new row
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Source]}
  contexts:
    r:
      place: web::app::transactions
---

# Import and create missing categories and accounts

## Trigger

The owner ticks the option to create what is missing.

## Outcome

Unknown category and account names become new categories and accounts before the rows are saved.

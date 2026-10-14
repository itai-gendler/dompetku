---
kind: primary
routes:
  r: Web
steps:
- text: The Owner exports the month
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Product builds the CSV of each Transaction
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Currency, Date, Description, Merchant, Notes]}
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
---

# Export transactions as CSV

## Trigger

The owner exports a month.

## Outcome

A CSV file of that month's transactions downloads.

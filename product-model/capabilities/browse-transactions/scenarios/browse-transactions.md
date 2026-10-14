---
kind: primary
routes:
  r: Web
steps:
- text: The Owner filters by month and searches a receipt item name
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Owner reads the matching Transaction list
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Currency, Date, Description, Merchant, Receipt items]}
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
---

# Browse and search transactions

## Trigger

The owner opens Transactions and searches.

## Outcome

Matching transactions are listed newest first, a page at a time.

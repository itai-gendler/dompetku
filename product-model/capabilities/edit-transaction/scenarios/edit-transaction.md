---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Transaction and saves
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Currency, Date, Description]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product keeps the change with a new IDR amount
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: changes, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Receipt photos]}
  contexts:
    r:
      place: web::app::transactions
---

# Edit a transaction

## Trigger

The owner corrects a transaction.

## Outcome

The transaction and the balances it touches reflect the change.

## Edge cases

- Moving an expense to another account without picking a pocket drops its old pocket.

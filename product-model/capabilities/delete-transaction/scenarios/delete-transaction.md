---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Transaction and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Product removes the Transaction and any receipt photo no other transaction uses
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: removes}
  contexts:
    r:
      place: web::app::transactions
---

# Delete a transaction

## Trigger

The owner deletes a transaction and confirms.

## Outcome

The transaction is gone and the balances it touched are restored.

---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner deletes a split part and chooses the whole group
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Split group]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product removes every Transaction of the split group
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: removes}
  contexts:
    r:
      place: web::app::transactions
---

# Delete every part of a split

## Trigger

The owner deletes one part of a split and chooses the whole receipt.

## Outcome

Every transaction of the split group is gone.

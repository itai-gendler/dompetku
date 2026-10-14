---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Gold trade and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: gold-trade, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::gold
- text: The Product removes it with its linked Transaction
  kind: product
  actor: owner
  entities:
  - {entity: gold-trade, effect: removes}
  - {entity: transaction, effect: removes, with: gold-trade}
  contexts:
    r:
      place: web::app::gold
---

# Delete a gold trade

## Trigger

The owner deletes a trade and confirms.

## Outcome

The trade and its linked transaction are gone.

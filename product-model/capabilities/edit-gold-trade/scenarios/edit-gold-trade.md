---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Gold trade
  kind: actor
  actor: owner
  entities:
  - {entity: gold-trade, effect: reads, facts: [Kind, Grams, Price per gram, Total]}
  contexts:
    r:
      place: web::app::gold
- text: The Product keeps the change and updates the linked transaction
  kind: product
  actor: owner
  entities:
  - {entity: gold-trade, effect: changes, facts: [Kind, Date, Grams, Price per gram, Total, Place, Gold type, Product number, Notes]}
  - {entity: transaction, effect: changes, facts: [Kind, Amount, Amount in IDR, Date, Description, Notes]}
  contexts:
    r:
      place: web::app::gold
---

# Edit a gold trade

## Trigger

The owner corrects a trade's grams or price.

## Outcome

The trade and its linked transaction show the new values.

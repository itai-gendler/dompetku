---
kind: primary
routes:
  r: Web
steps:
- text: The Product takes today's kept prices, or fetches and keeps them once for the day
  kind: product
  actor: owner
  entities:
  - {entity: gold-price, effect: creates, facts: [Source, Date, Sell price, Buyback price, Estimated]}
  contexts:
    r:
      place: web::app::gold
- text: The Owner reads the holdings, each Gold price and each Gold trade
  kind: actor
  actor: owner
  entities:
  - {entity: gold-price, effect: reads, facts: [Source, Date, Sell price, Buyback price, Estimated]}
  - {entity: gold-trade, effect: reads, facts: [Kind, Date, Grams, Price per gram, Total, Place]}
  contexts:
    r:
      place: web::app::gold
---

# See gold holdings and prices

## Trigger

The owner opens Gold.

## Outcome

Holdings, today's prices, current value, unrealised profit and the trades are shown.

---
kind: edge
routes:
  r: Web
steps:
- text: The Owner opens Gold
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::gold
- text: A price source does not answer today
  kind: condition
  actor: owner
  entities:
  - {entity: gold-price, effect: reads, facts: [Date]}
  contexts:
    r:
      place: web::app::gold
- text: The Product shows the last kept Gold price, or an estimate marked as such
  kind: product
  actor: owner
  entities:
  - {entity: gold-price, effect: reads, facts: [Estimated]}
  contexts:
    r:
      place: web::app::gold
---

# A price source cannot be reached

## Trigger

The world or Antam source does not answer today.

## Outcome

The last kept price is shown with its date; without one, Antam is estimated from the world price, and with neither the value waits for a price.

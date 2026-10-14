---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner enters a sell without an account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::gold
- text: The Product keeps the Gold trade only
  kind: product
  actor: owner
  entities:
  - {entity: gold-trade, effect: creates, facts: [Kind, Date, Grams, Price per gram, Total, Place, Gold type, Product number, Notes]}
  contexts:
    r:
      place: web::app::gold
---

# Record a gold sale without an account

## Trigger

The owner records a sale and chooses no account.

## Outcome

Holdings drop at the average cost, the realised profit grows, and no transaction is recorded.

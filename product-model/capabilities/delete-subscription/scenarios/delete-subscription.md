---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Subscription and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::subscriptions
- text: The Product removes it
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: removes}
  contexts:
    r:
      place: web::app::subscriptions
---

# Delete a subscription

## Trigger

The owner deletes a subscription and confirms.

## Outcome

It is gone; its payment transactions remain.

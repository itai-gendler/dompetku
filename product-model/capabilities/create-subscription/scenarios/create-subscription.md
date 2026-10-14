---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the name, amount, tax, currency, cycle, interval and next bill
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::subscriptions
- text: The Product keeps the Subscription
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: creates, facts: [Name, Amount, Tax percent, Currency, Cycle, Interval, Next due date, Active, Notes]}
  contexts:
    r:
      place: web::app::subscriptions
---

# Add a subscription

## Trigger

The owner adds a subscription.

## Outcome

It is listed with its price including tax and its monthly equivalent.

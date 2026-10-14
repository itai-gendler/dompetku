---
kind: primary
routes:
  r: Web
steps:
- text: The Owner taps Pay on the Subscription
  kind: actor
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: [Name, Amount, Tax percent, Next due date]}
  contexts:
    r:
      place: web::app::subscriptions
- text: The Product records the expense with tax and moves the next bill on
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source]}
  - {entity: subscription, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: web::app::subscriptions
---

# Pay a subscription

## Trigger

The owner taps Pay on a subscription.

## Outcome

An expense is recorded and the next bill date moves on by one interval.

---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Subscription
  kind: actor
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: [Name, Amount, Next due date, Active]}
  contexts:
    r:
      place: web::app::subscriptions
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: changes, facts: [Name, Amount, Tax percent, Currency, Cycle, Interval, Next due date, Active, Notes]}
  contexts:
    r:
      place: web::app::subscriptions
---

# Edit a subscription

## Trigger

The owner edits a subscription.

## Outcome

It shows the new details; an inactive one stops appearing as a bill.

---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner taps Pay on a due Subscription
  kind: actor
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: [Name, Amount, Next due date]}
  contexts:
    r:
      place: web::app::reminders
- text: The Product records the expense and moves the next bill on
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source]}
  - {entity: subscription, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: web::app::reminders
---

# Pay a subscription from Reminders

## Trigger

A subscription bill is due and the owner taps Pay in Reminders.

## Outcome

The bill is paid and leaves the reminders until the next one is near.

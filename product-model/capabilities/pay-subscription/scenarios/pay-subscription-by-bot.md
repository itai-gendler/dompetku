---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /bayar with part of the name
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: Exactly one Subscription or debt matches the name, and it is a Subscription
  kind: condition
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: [Name]}
  - {entity: debt, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
- text: The Product records the expense and moves the next bill on
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source]}
  - {entity: subscription, effect: changes, facts: [Next due date]}
  contexts:
    r:
      place: telegram-bot
---

# Pay a subscription with /bayar

## Trigger

The owner sends "/bayar netflix" or "sudah bayar netflix".

## Outcome

The bill is recorded at once, without a preview, and the bot names the next bill date.

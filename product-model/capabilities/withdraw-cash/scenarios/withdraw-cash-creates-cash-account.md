---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /tarik 200rb
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product creates the cash Account Tunai
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: creates, facts: [Name, Type, Currency, Initial balance]}
  contexts:
    r:
      place: telegram-bot
- text: The Product records the transfer from the first bank account into it
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Source]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
---

# The first withdrawal creates a cash account

## Trigger

No unarchived cash account exists yet.

## Outcome

A cash account named Tunai is created and receives the transfer.

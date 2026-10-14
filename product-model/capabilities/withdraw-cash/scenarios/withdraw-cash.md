---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner sends /tarik with an amount and an account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
- text: The Product records a transfer from the named Account into the first cash account
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Type]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Source]}
  contexts:
    r:
      place: telegram-bot
---

# Record a cash withdrawal

## Trigger

The owner sends "/tarik 500rb dari BCA".

## Outcome

A transfer into the cash account is recorded and the bot confirms it.

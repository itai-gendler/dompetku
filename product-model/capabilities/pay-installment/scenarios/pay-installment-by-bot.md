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
- text: Exactly one subscription or Debt matches the name, and it is a Debt
  kind: condition
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: [Name]}
  - {entity: debt, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
- text: The Product records the expense and the Installment payment
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source], with: installment-payment}
  - {entity: installment-payment, effect: creates, facts: [Installment number, Amount, Paid date]}
  contexts:
    r:
      place: telegram-bot
---

# Pay an installment with /bayar

## Trigger

The owner sends "/bayar kredivo".

## Outcome

The installment is recorded at once, without a preview, and the bot names which installment it was.

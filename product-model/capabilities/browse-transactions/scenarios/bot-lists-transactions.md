---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /pengeluaran with a period
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with the period's total and up to 20 Transaction lines
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date, Description, Merchant]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for a list

## Trigger

The owner sends /pengeluaran minggu or /pemasukan bulan.

## Outcome

The bot replies with the total and the first 20 transactions of the period.

## Edge cases

- An unknown period is answered with the periods the bot understands.

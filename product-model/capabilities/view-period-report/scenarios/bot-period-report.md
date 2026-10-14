---
kind: primary
routes:
  r: Telegram
steps:
- text: The Owner sends /minggu
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with the period's income, expense, change, daily average, categories and largest expenses
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date, Description, Merchant]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for a report

## Trigger

The owner sends /minggu.

## Outcome

The bot replies with the week's figures; a month report also shows the total balance.

## Edge cases

- Making a report first posts due monthly fees and automatic recurring occurrences.
- Past 50,000 transactions in a period the report says its totals are incomplete.

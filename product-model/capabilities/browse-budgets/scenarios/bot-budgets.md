---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner sends /budget
  kind: actor
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: []}
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with each Budget's use this month
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: [Monthly limit, Alert percent, Spent this month, Effective limit]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
---

# Ask the bot for budgets

## Trigger

The owner sends /budget.

## Outcome

The bot lists every budget, fullest first, marked at the warning and at the limit.

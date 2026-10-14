---
kind: validation
routes:
  r: Telegram
steps:
- text: The Owner sends /bayar with a name several bills share
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product replies with the matching names and records nothing
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: reads, facts: [Name]}
  - {entity: debt, effect: reads, facts: [Name]}
  contexts:
    r:
      place: telegram-bot
---

# The name matches several bills

## Trigger

The owner's /bayar name matches no bill or more than one.

## Outcome

Nothing is recorded; the bot lists the matches or says none was found.

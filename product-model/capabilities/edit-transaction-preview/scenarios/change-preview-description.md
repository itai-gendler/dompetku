---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner taps Keterangan
  kind: actor
  actor: owner
  entities:
  - {entity: transaction-preview, effect: reads, facts: [Description]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product asks for the new description and waits for the next message in this chat
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, facts: [Awaiting description]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Owner sends the new description within 10 minutes
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product stores the description, stops waiting and sends the refreshed preview
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, facts: [Description, Awaiting description]}
  contexts:
    r:
      place: telegram-bot
---

# Send a new description

## Trigger

The owner taps Keterangan and sends "dini bayar baju".

## Outcome

A refreshed preview shows the new description; amount, merchant, items and photo stay.

## Edge cases

- A message after 10 minutes is read as a new transaction instead.
- The same message delivered twice refreshes the preview again and never runs a command.

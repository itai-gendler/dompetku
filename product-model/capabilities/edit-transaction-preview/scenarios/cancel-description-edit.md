---
kind: edge
routes:
  r: Telegram
steps:
- text: The Owner sends /batal while the description is awaited
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: telegram-bot
- text: The Product stops waiting and sends the unchanged preview
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, facts: [Awaiting description]}
  contexts:
    r:
      place: telegram-bot
---

# Cancel the description edit

## Trigger

After tapping Keterangan the owner sends /batal or taps Kembali, another button or another command.

## Outcome

The preview is unchanged and the next message is a transaction again; /batal here never undoes a transaction.

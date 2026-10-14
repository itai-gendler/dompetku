---
kind: alternative
routes:
  r: Telegram
steps:
- text: The Owner taps Akun and picks an Account from the list
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: transaction-preview, effect: reads, facts: [Account]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
- text: The Product updates the preview
  kind: product
  actor: owner
  entities:
  - {entity: transaction-preview, effect: changes, facts: [Account]}
  contexts:
    r:
      place: telegram-bot::transaction-preview
---

# Pick another account

## Trigger

The owner taps Akun on a preview.

## Outcome

The preview shows the chosen account.

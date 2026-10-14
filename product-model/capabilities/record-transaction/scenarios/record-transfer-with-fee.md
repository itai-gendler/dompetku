---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner enters a transfer from one Account to another and picks a fee
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Transfer fee presets]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product saves the transfer and, with it, the fee as an expense in Biaya Admin
  kind: product
  actor: owner
  entities:
  - {entity: transaction, as: transfer, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Source]}
  - {entity: transaction, as: fee, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Notes, Source], with: transfer}
  contexts:
    r:
      place: web::app::transactions
---

# Record a transfer with a fee

## Trigger

The owner moves money between two accounts and picks a transfer fee preset.

## Outcome

The transfer and a separate fee expense in Biaya Admin from the source account are saved together.

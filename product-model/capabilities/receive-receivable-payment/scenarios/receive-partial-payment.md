---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the amount, date and the Account it came into
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: [Remaining]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::receivables
- text: The Product keeps the Receivable payment and, with it, the income in Piutang
  kind: product
  actor: owner
  entities:
  - {entity: receivable-payment, effect: creates, facts: [Amount, Paid date]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Notes, Source], with: receivable-payment}
  contexts:
    r:
      place: web::app::receivables
---

# Receive a partial payment

## Trigger

The borrower pays back part of the loan into BCA.

## Outcome

The payment is listed, the remaining amount drops and the account shows the income.

---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters a buy with grams, price per gram, place and the Account it was paid from
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::gold
- text: The Product keeps the Gold trade and, with it, the expense in Emas
  kind: product
  actor: owner
  entities:
  - {entity: gold-trade, effect: creates, facts: [Kind, Date, Grams, Price per gram, Total, Place, Gold type, Product number, Notes]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Notes, Source], with: gold-trade}
  contexts:
    r:
      place: web::app::gold
---

# Record a gold purchase from an account

## Trigger

The owner records buying 5 g of Antam gold paid from BCA.

## Outcome

The purchase adds to holdings and an expense of the total appears on the account.

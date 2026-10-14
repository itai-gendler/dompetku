---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner enters the receipt total and divides it over two or more categories
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product saves one expense per part, all in one split group
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Receipt photos, Source, Split group]}
  contexts:
    r:
      place: web::app::transactions
---

# Record a split expense

## Trigger

The owner splits one receipt across several categories.

## Outcome

Two to twenty expenses share one split group and the receipt photos; their parts add up to the receipt total.

## Edge cases

- Only an expense can be split.

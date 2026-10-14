---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner picks a Pocket of the chosen account for the expense
  kind: actor
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Pocket belongs to the expense's account and is not archived
  kind: condition
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: [Archived]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Product saves the Transaction in the Pocket
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source]}
  - {entity: pocket, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
---

# Record an expense from a pocket

## Trigger

The owner picks one of the account's pockets for an expense.

## Outcome

The expense counts against the pocket; the first time this month the pocket falls to its threshold or to zero, the save warns once for that level.

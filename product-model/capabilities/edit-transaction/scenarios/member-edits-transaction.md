---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member holds Manage on the accounts the Transaction touches
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: transaction, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Family member changes the amount and saves
  kind: actor
  actor: family-member
  entities:
  - {entity: transaction, effect: reads, facts: [Amount]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product keeps the change
  kind: product
  actor: family-member
  entities:
  - {entity: transaction, effect: changes, facts: [Amount, Amount in IDR]}
  contexts:
    r:
      place: web::app::transactions
---

# A member edits a transaction

## Trigger

A family member with Manage on the transaction's accounts edits it.

## Outcome

The change is kept; pocket warnings apply as on recording.

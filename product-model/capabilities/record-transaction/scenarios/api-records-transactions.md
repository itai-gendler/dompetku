---
kind: primary
routes:
  r: API
steps:
- text: The n8n automation posts transactions with account and category names
  kind: actor
  actor: n8n-automation
  entities:
  - {entity: transaction, effect: reads, facts: []}
  - {entity: category, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: automation-api
- text: The Product creates each named Category that does not exist yet
  kind: product
  actor: n8n-automation
  entities:
  - {entity: category, effect: creates, facts: [Name, Kind]}
  contexts:
    r:
      place: automation-api
- text: The Product matches each Account by name and saves each Transaction
  kind: product
  actor: n8n-automation
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source]}
  contexts:
    r:
      place: automation-api
---

# n8n records transactions

## Trigger

An n8n workflow posts one transaction, or a list of up to 100.

## Outcome

Each transaction is saved with the account and category matched by name; a category name that does not exist yet is created.

## Edge cases

- A request without a valid n8n API key, or on a demo instance, is refused before anything is read.

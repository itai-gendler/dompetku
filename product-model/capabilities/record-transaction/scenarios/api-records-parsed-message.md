---
kind: alternative
routes:
  r: API
steps:
- text: The n8n automation posts a chat text or receipt image
  kind: actor
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
- text: The Product has the language model read it onto existing categories and accounts and saves the Transaction
  kind: product
  actor: n8n-automation
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: automation-api
---

# n8n records a chat message read by AI

## Trigger

An n8n workflow posts a chat text such as "makan siang 25rb" or a receipt image.

## Outcome

The AI reading is saved straight away as a transaction, unless the workflow asks only for the reading.

## Edge cases

- A text or image without a readable amount is answered with the reading and nothing is saved.

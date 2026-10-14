---
kind: alternative
routes:
  r: API
steps:
- text: The n8n automation asks for a period's report
  kind: actor
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
- text: The Product returns the period's figures and a message
  kind: product
  actor: n8n-automation
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: automation-api
---

# n8n fetches a report

## Trigger

An n8n schedule asks for last week's report.

## Outcome

The figures come back with a chat-ready message.

## Edge cases

- An unknown period is refused.

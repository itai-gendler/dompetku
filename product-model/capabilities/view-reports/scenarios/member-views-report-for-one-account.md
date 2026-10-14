---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member chooses one shared Account
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::reports
- text: The Product limits the report to that Account within the member's access
  kind: product
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: transaction, effect: reads, facts: [Amount in IDR, Date]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::reports
---

# A member filters a report by account

## Trigger

A family member chooses one of their accounts.

## Outcome

The report covers that account only; choosing an account outside their access shows an empty report.

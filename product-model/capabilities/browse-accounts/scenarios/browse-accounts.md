---
kind: primary
routes:
  r: Web
steps:
- text: The Owner reads each Account with its balance
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Type, Currency, Balance, Archived, Monthly fee, Monthly fee day]}
  contexts:
    r:
      place: web::app::accounts
---

# Browse accounts and balances

## Trigger

The owner opens Accounts.

## Outcome

Every account is listed with type, currency, balance, archive mark and monthly fee.

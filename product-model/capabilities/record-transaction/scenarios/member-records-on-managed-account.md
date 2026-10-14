---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member holds Manage on the Account
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Family member enters the expense on that Account
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product saves the Transaction
  kind: product
  actor: family-member
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source]}
  contexts:
    r:
      place: web::app::transactions
---

# A member records on a shared account

## Trigger

A family member with Manage on an account records an expense on it.

## Outcome

The expense is saved like the owner's; the member gets pocket warnings but never budget warnings.

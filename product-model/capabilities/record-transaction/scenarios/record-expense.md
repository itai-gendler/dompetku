---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the amount, account, category, date and description of an expense
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
- text: The Product saves the Transaction with its amount in IDR at the day's rate
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source]}
  contexts:
    r:
      place: web::app::transactions
---

# Record an expense

## Trigger

The owner records an expense on the Transactions page.

## Outcome

The expense is saved with its IDR amount and the account's balance drops.

## Decision points

### Budget warning

Does this expense, dated this month, push its category's budget past the warning or the limit for the first time this month?

- it does → the save confirms with a budget warning for each level crossed
- it does not → the save confirms with no budget warning

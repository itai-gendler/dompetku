---
kind: primary
routes:
  r: Web
steps:
- text: The Owner picks a backup file and chooses Merge
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::backup
- text: The Product adds or updates each Account from the file
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: creates, facts: [Name, Type, Currency, Initial balance, Color, Archived, Transfer fee presets, Top-up fee presets, Monthly fee, Monthly fee day]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product adds or updates each Category from the file
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: creates, facts: [Name, Kind, Color]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product adds or updates each Transaction from the file
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source, Split group]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product adds or updates each Budget from the file
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: creates, facts: [Monthly limit, Alert percent, Rollover]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product adds or updates each Goal from the file
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: creates, facts: [Name, Target amount, Saved amount, Deadline, Color]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product adds or updates each Subscription from the file
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: creates, facts: [Name, Amount, Tax percent, Currency, Cycle, Interval, Active, Notes]}
  contexts:
    r:
      place: web::administration::backup
---

# Merge a backup

## Trigger

The owner picks a backup file and chooses Merge.

## Outcome

Rows from the file are added or updated and nothing else is touched; tables the database does not have yet are skipped and named.

## Edge cases

- The rest of the data in the file — debts, recurring transactions, pockets and the others — is restored the same way.

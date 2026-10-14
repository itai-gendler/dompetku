---
kind: primary
routes:
  r: Web
steps:
- text: The dashboard, the reminders or a bot report is needed after the fee day of an Account this month
  kind: condition
  unattended: true
  entities:
  - {entity: account, effect: reads, facts: [Monthly fee, Monthly fee day]}
  contexts:
    r:
      place: web::app
- text: The Product creates the Category Biaya Admin when it does not exist
  kind: product
  entities:
  - {entity: category, effect: creates, facts: [Name, Kind]}
  contexts:
    r:
      place: web::app
- text: The Product records the fee as an expense in Biaya Admin on the fee day, once for this month
  kind: product
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Notes, Source]}
  contexts:
    r:
      place: web::app
---

# Post a due monthly fee

## Trigger

The dashboard, the reminders or a bot report is needed after an account's fee day this month.

## Outcome

One fee expense per account per month exists on the fee day; later runs add nothing.

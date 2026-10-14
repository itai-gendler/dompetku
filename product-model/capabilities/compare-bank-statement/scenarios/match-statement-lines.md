---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member holds Wallet access to the Account
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Family member imports the statement lines of the Account
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product pairs each line with a Transaction of the same amount dated within two days and lists what is left on either side
  kind: product
  actor: family-member
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Date, Description]}
  contexts:
    r:
      place: web::app::account-detail
---

# Match imported statement lines

## Trigger

A family member who may see the account imports the bank's statement lines.

## Outcome

Lines are paired with transactions of the period; unmatched lines and unmatched transactions are listed, and a bank-only line can be recorded from there.

## Edge cases

- A file without the required columns, or without a valid line, is refused with the reason.

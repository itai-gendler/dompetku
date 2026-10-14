---
kind: primary
routes:
  r: Web
steps:
- text: The Product gathers the bills due in the window and the budgets past their warning
  kind: product
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date]}
  - {entity: subscription, effect: reads, facts: [Name, Amount, Tax percent, Next due date, Active]}
  - {entity: recurring-transaction, effect: reads, facts: [Name, Amount, Next due date, Auto-post]}
  - {entity: account, effect: reads, facts: [Name, Monthly fee, Monthly fee day]}
  - {entity: budget, effect: reads, facts: [Spent this month, Alert percent, Effective limit]}
  contexts:
    r:
      place: web::app::reminders
- text: The Owner reads each bill and switches the window to 7 or 90 days
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date]}
  - {entity: subscription, effect: reads, facts: [Name, Amount, Next due date]}
  - {entity: recurring-transaction, effect: reads, facts: [Name, Amount, Next due date]}
  contexts:
    r:
      place: web::app::reminders
---

# See upcoming bills

## Trigger

The owner opens Reminders.

## Outcome

Bills of the next 30 days are listed by due date with days left or days late, budgets past their warning are flagged, and the bill total is shown.

## Edge cases

- Automatic recurring items never appear; they are posted when due.
- Gathering the reminders first posts due monthly fees and automatic recurring occurrences.

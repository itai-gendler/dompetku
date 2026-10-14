---
domain: recurring-transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/recurring.server.ts#applyRecurring
- kind: code
  role: implementation
  target: src/lib/recurring.ts#dueOccurrences
---

# Post due recurring transactions

Automatic schedules have their due occurrences recorded, each dated on its due day, the next time the owner's dashboard, the reminders or a bot report is needed. At most the latest 12 missed occurrences of one schedule are posted in one run; a schedule past its end date is paused.

---
domain: recurring-transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/recurring.server.ts#setRecurringActive
---

# Pause recurring transaction

The owner pauses a schedule.

---
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/recurring.server.ts#postRecurringNow
---

# Record recurring transaction

Record the current occurrence of a schedule now, from the schedule's list or from Reminders, and move it to the next one. Each occurrence is recorded once.

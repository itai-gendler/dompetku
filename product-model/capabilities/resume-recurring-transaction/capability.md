---
domain: recurring-transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/recurring.ts#resumeNextDue
---

# Resume recurring transaction

The owner resumes a paused schedule; occurrences missed while paused are skipped.

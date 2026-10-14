---
appliesTo:
- {type: capability, id: post-due-recurring-transactions}
- {type: capability, id: resume-recurring-transaction}
- {type: entity, id: recurring-transaction}
references:
- kind: code
  role: implementation
  target: src/lib/recurring.ts#RECURRING_CATCHUP_CAP
- kind: code
  role: implementation
  target: src/lib/recurring.ts#resumeNextDue
---

# Missed recurring occurrences are limited

An automatic schedule posts at most its latest 12 missed occurrences in one run. Resuming a paused schedule skips everything missed while paused.

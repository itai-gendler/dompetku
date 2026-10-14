---
domain: recurring-transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/recurring.tsx
- kind: code
  role: implementation
  target: src/lib/schemas.ts#recurringSchema
---

# Edit recurring transaction

The owner changes a schedule.

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

# Delete recurring transaction

The owner deletes a schedule; posted transactions stay.

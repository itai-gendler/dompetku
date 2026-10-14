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

# Create recurring transaction

The owner schedules a repeating income, expense or transfer: every N weeks, months or years, anchored to a day of the month, from a start date to an optional end date, posted automatically or recorded by hand.

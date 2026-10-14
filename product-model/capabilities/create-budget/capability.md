---
domain: budgets
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/budgets.tsx
- kind: code
  role: implementation
  target: src/lib/schemas.ts#budgetSchema
---

# Create budget

The owner sets a monthly limit for an expense category, the warning percent and whether leftovers roll over.

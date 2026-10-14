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

# Edit budget

The owner changes a budget's limit, warning percent or rollover.

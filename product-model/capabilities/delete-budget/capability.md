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

# Delete budget

The owner removes a budget.

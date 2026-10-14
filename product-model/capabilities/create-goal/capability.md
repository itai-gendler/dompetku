---
domain: goals
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/goals.tsx
- kind: code
  role: implementation
  target: src/lib/schemas.ts#goalSchema
---

# Create goal

The owner adds a savings goal with a target, an optional deadline and an optional savings account.

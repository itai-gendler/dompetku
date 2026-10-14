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

# Edit goal

The owner changes a goal, including the saved amount, without moving money.

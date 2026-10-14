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

# Delete goal

The owner deletes a goal; transfers made for it stay.

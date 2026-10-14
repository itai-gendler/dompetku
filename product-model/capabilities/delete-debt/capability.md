---
domain: debts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/debts.tsx
- kind: code
  role: implementation
  target: src/lib/schemas.ts#debtSchema
---

# Delete debt

The owner deletes a debt with its payment history.

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

# Create debt

The owner adds a debt with its installment amount, number of installments, first installment month and due day.

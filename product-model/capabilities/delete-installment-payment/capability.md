---
domain: debts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#deleteDebtPayment
---

# Delete installment payment

The owner removes a recorded installment payment, together with its expense. The debt is active afterwards.

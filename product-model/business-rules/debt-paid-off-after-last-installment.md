---
appliesTo:
- {type: capability, id: pay-installment}
- {type: entity, id: debt}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#payDebt
---

# A debt is paid off when its last installment is paid

Paying the installment that completes the number of installments marks the debt paid off; a paid-off debt takes no more payments.

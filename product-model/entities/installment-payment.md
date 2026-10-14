---
domain: debts
relations:
- {entity: transaction, verb: is recorded as, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#payDebt
---

# Installment payment

The payment of one installment of a debt, recorded together with its expense transaction.

## Information kept

- **Installment number** — which installment it pays, counted from 1
- **Amount** — the installment amount
- **Paid date** — the day it was paid

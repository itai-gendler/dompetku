---
appliesTo:
- {type: capability, id: import-transactions}
- {type: entity, id: transaction, effect: creates}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#importTransactions
---

# An import never records the same transaction twice

A CSV row with the same date, type, amount, currency and description as a recorded transaction, or as an earlier row, is skipped.

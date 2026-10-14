---
domain: receivables
relations:
- {entity: transaction, verb: is received as, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#payReceivable
---

# Receivable payment

One payment received on a receivable; with an account it is also an income in category Piutang.

## Information kept

- **Amount** — the amount received
- **Paid date** — the day it was received

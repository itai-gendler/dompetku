---
domain: receivables
relations:
- {entity: receivable-payment, verb: is repaid by, cardinality: one-to-many}
- {entity: transaction, verb: is lent as, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#receivableSchema
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#saveReceivable
---

# Receivable

Money lent to someone (Piutang), repaid in one or more payments.

## Information kept

- **Purpose** — what the money was for
- **Borrower** — who borrowed it
- **Amount** — the amount lent
- **Currency** — IDR or USD
- **Lent date** — the day it was lent
- **Due date** — an optional day it should be back
- **Notes** — free text
- **Paid** — the sum of payments received
- **Remaining** — amount minus payments, never below zero

## States

### Active

Money is still owed.

### Paid

Repaid in full, or marked paid by the owner.

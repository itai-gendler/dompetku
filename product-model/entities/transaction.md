---
domain: transactions
relations:
- {entity: transaction, verb: charges, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#transactionSchema
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#insertTransaction
---

# Transaction

One income, expense or transfer between two accounts. A split receipt is several expense transactions sharing a split group; a transfer or top-up fee is its own expense in category Biaya Admin, created with the transaction it belongs to.

## Information kept

- **Kind** — income, expense or transfer
- **Amount** — a positive amount in the transaction's currency
- **Currency** — IDR or USD
- **Amount in IDR** — the amount converted at the day's USD rate, used by every total
- **Date** — the day it happened
- **Description** — free text
- **Merchant** — who was paid or who paid
- **Notes** — free text
- **Receipt items** — item lines read from a receipt; searchable by name
- **Receipt photos** — up to five private photos
- **Source** — where it was recorded: web, telegram, whatsapp, ocr, n8n or import
- **Split group** — shared by the parts of one split receipt

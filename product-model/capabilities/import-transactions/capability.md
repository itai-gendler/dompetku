---
domain: transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#importTransactions
- kind: code
  role: implementation
  target: src/lib/csv.ts
- kind: code
  role: implementation
  target: src/components/csv-import.tsx
---

# Import transactions

The owner imports transactions from a CSV file (date, type, amount, category, account, notes, currency). A preview shows the valid rows; rows identical to a recorded transaction are skipped; missing categories and accounts are created only when the owner ticks that option.

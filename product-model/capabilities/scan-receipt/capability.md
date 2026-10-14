---
domain: transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#scanReceipt
- kind: code
  role: implementation
  target: src/lib/ocr.server.ts
---

# Scan receipt

The owner photographs a receipt in the transaction form; the language model reads merchant, date, total, items and category onto existing categories and fills the form. Nothing is saved until the owner saves the transaction.

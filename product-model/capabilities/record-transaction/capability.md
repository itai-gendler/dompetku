---
domain: transactions
availability:
- place: web::app
- place: automation-api
references:
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#saveTransaction
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#insertTransaction
- kind: code
  role: implementation
  target: src/components/transaction-dialog.tsx
- kind: code
  role: implementation
  target: src/routes/api/public/n8n/transactions.ts
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#createFromExternal
- kind: code
  role: implementation
  target: src/lib/split.server.ts#saveSplitTransaction
---

# Record transaction

Record an income, expense or transfer: amount and currency, account (and destination account for a transfer), category, optional pocket of the account, date, description, merchant, notes and up to five receipt photos. A transfer or top-up can carry a fee, recorded as its own expense in Biaya Admin. An expense can be split across categories. The owner's n8n workflows record transactions through the automation API, matching accounts and categories by name.

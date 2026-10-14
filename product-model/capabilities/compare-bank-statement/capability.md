---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/components/account-reconcile.tsx
- kind: code
  role: implementation
  target: src/lib/account-report.ts
---

# Compare bank statement

Check an account against the bank: enter the statement's date and closing balance to see the app's balance for that date and the difference, or import the statement's lines to see which match recorded transactions, which exist only at the bank and which only in the app.

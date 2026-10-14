---
domain: accounts
references:
- kind: code
  role: implementation
  target: src/lib/account-report.server.ts#saveReconciliation
- kind: code
  role: implementation
  target: src/lib/account-report.ts
---

# Reconciliation

A saved check of an account against a bank statement: the statement's closing balance on a date beside the balance the app had for that date.

## Information kept

- **As-of date** — the statement date
- **Statement balance** — the closing balance on the bank statement
- **App balance** — the account's balance in the app at the end of that date
- **Difference** — statement balance minus app balance; positive means the bank recorded more

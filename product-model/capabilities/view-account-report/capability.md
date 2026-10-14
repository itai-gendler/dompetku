---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/account-report.server.ts#computeAccountReport
- kind: code
  role: implementation
  target: src/routes/_app/accounts_.$id.tsx
---

# View account report

See one account's report: its balance month by month over 12 months, the month's money in and out, spending per category and the latest reconciliation. Anyone who may see the account opens it.

---
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/rekap.tsx
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeYearly
---

# View yearly recap

The owner sees a printable summary of one year, for every account or one, and exports it as CSV.

---
entities:
- {entity: transaction, shows: [Amount in IDR, Date]}
- {entity: category, shows: [Name]}
entryPoints:
- web: /rekap
references:
- kind: code
  role: implementation
  target: src/routes/_app/rekap.tsx
---

# Yearly recap

A printable summary of one year, for all accounts or one, with CSV export.

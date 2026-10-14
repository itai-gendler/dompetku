---
entities:
- {entity: transaction, shows: [Kind, Amount, Currency, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Split group], collects: [Kind, Amount, Currency, Date, Description, Merchant, Notes, Receipt items, Receipt photos]}
- {entity: account, shows: [Name, Transfer fee presets, Top-up fee presets]}
- {entity: category, shows: [Name]}
- {entity: pocket, shows: [Name]}
entryPoints:
- web: /transactions
references:
- kind: code
  role: implementation
  target: src/routes/_app/transactions.tsx
- kind: code
  role: implementation
  target: src/components/transaction-dialog.tsx
---

# Transactions

Every transaction the person may see, with search (including receipt item names), filters, sorting and paging, and the form to record or edit one.

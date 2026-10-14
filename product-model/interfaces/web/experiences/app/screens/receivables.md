---
entities:
- {entity: receivable, shows: [Purpose, Borrower, Amount, Currency, Lent date, Due date, Paid, Remaining], collects: [Purpose, Borrower, Amount, Currency, Lent date, Due date, Notes]}
- {entity: receivable-payment, shows: [Amount, Paid date], collects: [Amount, Paid date]}
- {entity: account, shows: [Name]}
entryPoints:
- web: /receivables
references:
- kind: code
  role: implementation
  target: src/routes/_app/receivables.tsx
---

# Receivables

Money lent to others: what each borrower still owes, the due date and the payments received, with the total still outstanding in IDR.

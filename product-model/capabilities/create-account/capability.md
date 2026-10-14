---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/accounts.tsx
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#saveRow
---

# Create account

The owner adds a bank account, e-wallet, cash, credit card or investment account, with its currency, initial balance and optional fees.

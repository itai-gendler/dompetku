---
domain: accounts
relations:
- {entity: transaction, verb: holds, cardinality: one-to-many}
- {entity: transaction, verb: receives, cardinality: one-to-many}
- {entity: wallet-access, verb: grants, cardinality: one-to-many}
- {entity: pocket, verb: contains, cardinality: one-to-many}
- {entity: goal, verb: saves, cardinality: one-to-many}
- {entity: reconciliation, verb: is checked by, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#accountSchema
- kind: code
  role: implementation
  target: supabase/schema.sql
---

# Account

A place money is kept — a bank account, e-wallet, cash, credit card or investment — whose balance is its initial balance plus every transaction on it.

## Information kept

- **Name** — for example BCA, GoPay or Tunai
- **Type** — bank, e-wallet, cash, credit card, investment or other
- **Currency** — IDR or USD
- **Initial balance** — the balance before the first recorded transaction
- **Color** — a display color
- **Archived** — an archived account stays in history but is left out of balance totals and pickers
- **Transfer fee presets** — named fees offered when transferring out of this account
- **Top-up fee presets** — named fees offered when topping this account up
- **Monthly fee** — an admin fee charged automatically every month
- **Monthly fee day** — the day of the month the monthly fee is charged
- **Balance** — initial balance plus incomes and incoming transfers minus expenses and outgoing transfers

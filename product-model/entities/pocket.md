---
domain: accounts
relations:
- {entity: transaction, verb: earmarks, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: src/lib/pockets.ts
- kind: code
  role: implementation
  target: src/lib/pockets.server.ts#savePocket
---

# Pocket

A Kantong: part of one account's money earmarked for a purpose (Mandiri → Makan 500rb). It is not a budget; it belongs to exactly one account.

## Information kept

- **Name** — unique within its account; also the #tag used in the bot
- **Allocated amount** — the amount earmarked, in the account's currency
- **Low-balance threshold** — optional remaining amount at or below which the pocket is low
- **Period** — Monthly (starts fresh every month) or running (every pocket transaction ever counts)
- **Archived** — an archived pocket keeps its history but cannot be picked for new transactions
- **Remaining** — allocated amount minus pocket expenses and outgoing transfers plus pocket incomes in the period

---
domain: settings
relations:
- {entity: transaction, verb: classifies, cardinality: one-to-many}
- {entity: budget, verb: limits, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#categorySchema
---

# Category

A named income or expense category such as Makan or Gaji. Budgets are set per expense category.

## Information kept

- **Name** — unique together with its kind
- **Kind** — income or expense
- **Color** — a display color

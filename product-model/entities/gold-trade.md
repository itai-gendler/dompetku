---
domain: gold
relations:
- {entity: transaction, verb: is paid as, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#goldSchema
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#saveGold
- kind: code
  role: implementation
  target: src/lib/assets.ts#goldHoldings
---

# Gold trade

One purchase or sale of gold. With an account chosen, a buy is also an expense and a sale an income in category Emas, kept in step with the record.

## Information kept

- **Kind** — buy or sell
- **Date** — the day of the trade
- **Grams** — the weight, up to four decimals
- **Price per gram** — the price paid or received per gram
- **Total** — the amount paid or received; grams × price when left empty
- **Place** — where it was bought or sold
- **Gold type** — for example Antam or UBS
- **Product number** — the bar's serial number
- **Notes** — free text

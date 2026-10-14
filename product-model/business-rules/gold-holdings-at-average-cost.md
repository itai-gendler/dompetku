---
appliesTo:
- {type: capability, id: browse-gold-holdings}
- {type: entity, id: gold-trade}
references:
- kind: code
  role: implementation
  target: src/lib/assets.ts#goldHoldings
- kind: code
  role: implementation
  target: src/lib/assets.ts#goldValue
---

# Gold holdings use the average cost

A sale takes grams out at the running average buy price; the difference to the sale total is realised profit. Holdings are valued at today's buyback price.

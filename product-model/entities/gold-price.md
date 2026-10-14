---
domain: gold
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#getGoldPrices
---

# Gold price

A day's reference price per gram from one source, kept once per day per source.

## Information kept

- **Source** — the world price (XAU) or Antam
- **Date** — the day of the price
- **Sell price** — the price to buy gold at
- **Buyback price** — the price the seller pays back; holdings are valued at it
- **Estimated** — an Antam price worked out from the world price when Antam's own could not be fetched

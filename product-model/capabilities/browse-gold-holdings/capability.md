---
domain: gold
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#goldSummary
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#getGoldPrices
- kind: code
  role: implementation
  target: src/lib/assets.ts#goldHoldings
---

# Browse gold holdings

See grams held, cost, average buy price and realised profit (average-cost method), today's world (XAU) and Antam prices, the holdings' value at the buyback price with unrealised profit, and every trade, sortable and filterable by account.

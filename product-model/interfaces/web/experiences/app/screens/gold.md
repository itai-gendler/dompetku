---
entities:
- {entity: gold-trade, shows: [Kind, Date, Grams, Price per gram, Total, Place, Gold type, Product number], collects: [Kind, Date, Grams, Price per gram, Total, Place, Gold type, Product number, Notes]}
- {entity: gold-price, shows: [Source, Date, Sell price, Buyback price, Estimated]}
- {entity: account, shows: [Name]}
entryPoints:
- web: /gold
references:
- kind: code
  role: implementation
  target: src/routes/_app/gold.tsx
---

# Gold

Gold holdings — grams held, cost, average buy price and realised profit — today's world (XAU) and Antam prices with the current value and unrealised profit, and every purchase and sale.

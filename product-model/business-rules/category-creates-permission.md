---
appliesTo:
- {type: entity, id: category, effect: creates}
permits:
- actors: [owner]
- actors: [n8n-automation]
- unattended: true
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#ensureCategory
---

# Who creates categories

The owner creates categories. The owner's n8n workflows create one when a posted transaction names a category that does not exist, and the Product creates Biaya Admin when it posts a monthly account fee.

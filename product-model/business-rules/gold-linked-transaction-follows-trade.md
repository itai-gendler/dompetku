---
appliesTo:
- {type: capability, id: record-gold-trade}
- {type: capability, id: edit-gold-trade}
- {type: capability, id: delete-gold-trade}
- {type: entity, id: gold-trade}
references:
- kind: code
  role: implementation
  target: src/lib/assets.ts#goldLinkAction
---

# A gold trade's transaction follows the trade

With an account, a buy is an expense and a sale an income in Emas for the trade's total and date; editing the trade updates it, clearing the account or deleting the trade removes it.

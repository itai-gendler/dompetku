---
appliesTo:
- {type: capability, id: record-recurring-transaction}
- {type: capability, id: post-due-recurring-transactions}
- {type: entity, id: transaction, effect: creates}
references:
- kind: code
  role: implementation
  target: src/lib/recurring.ts#recurringExternalId
---

# Each recurring occurrence is recorded once

One occurrence of a schedule becomes at most one transaction, whether recorded by hand, posted automatically, retried or tapped twice.

---
appliesTo:
- {type: capability, id: receive-receivable-payment}
- {type: capability, id: cancel-receivable-payment}
- {type: entity, id: receivable}
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#payReceivable
---

# A receivable is paid once its payments reach the amount lent

A payment that brings the total received to the amount lent marks the receivable paid; cancelling a payment makes it active again.

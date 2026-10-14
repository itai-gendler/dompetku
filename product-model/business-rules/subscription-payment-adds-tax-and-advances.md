---
appliesTo:
- {type: capability, id: pay-subscription}
- {type: entity, id: subscription, facts: [Next due date]}
references:
- kind: code
  role: implementation
  target: src/lib/fees.ts#withTax
- kind: code
  role: implementation
  target: src/lib/subscriptions.ts
---

# Paying a subscription adds its tax and moves the next bill by its interval

A subscription payment records the price plus tax percent and moves the next bill date on by interval × cycle, keeping the day of the month.

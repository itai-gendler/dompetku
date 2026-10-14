---
appliesTo:
- {type: capability, id: post-monthly-account-fees}
- {type: entity, id: account, facts: [Monthly fee]}
references:
- kind: code
  role: implementation
  target: src/lib/fees.ts#dueMonthlyFees
---

# A monthly account fee is recorded once per month

An account's monthly fee becomes one expense per month on its fee day (the last day of a shorter month), never two.

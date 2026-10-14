---
appliesTo:
- {type: capability, id: browse-budgets}
- {type: entity, id: budget, facts: [Carried amount, Effective limit]}
references:
- kind: code
  role: implementation
  target: src/lib/budget.ts#rolloverCarry
- kind: code
  role: implementation
  target: src/lib/budget.ts#budgetPercent
---

# Rollover carries each month's remainder into the next

With rollover on, effective limit = monthly limit + carried amount, and each month's remainder (negative when overspent) carries into the next. The chain starts at the month the budget was created, looks back at most 12 months, and uses today's monthly limit for every month. An effective limit at or below zero counts as already exhausted.

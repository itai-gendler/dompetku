---
appliesTo:
- {type: capability, id: create-budget}
- {type: capability, id: edit-budget}
- {type: entity, id: budget, effect: creates}
references:
- kind: code
  role: implementation
  target: supabase/schema.sql
---

# A category has at most one budget

Each expense category has at most one budget.

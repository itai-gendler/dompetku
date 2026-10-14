---
appliesTo:
- {type: capability, id: delete-account}
- {type: capability, id: delete-category}
- {type: capability, id: delete-pocket}
- {type: entity, id: transaction}
references:
- kind: code
  role: implementation
  target: supabase/schema.sql
---

# Deleting an account, category or pocket keeps its transactions

Transactions outlive the account, category or pocket they belonged to and stay without it.

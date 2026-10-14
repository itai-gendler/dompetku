---
appliesTo:
- {type: entity, id: family-member, effect: creates}
permits:
- actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/users.functions.ts
---

# Only the owner adds family members

Only the owner adds family members.

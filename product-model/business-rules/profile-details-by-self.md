---
appliesTo:
- {type: entity, id: profile, effect: changes, facts: [Address, Profile photo]}
permits:
- related:
  - {verb: signs in as, entity: owner}
- related:
  - {verb: signs in as, entity: family-member}
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#saveProfile
---

# Only the person changes their own address and photo

Each person changes only their own address and profile photo.

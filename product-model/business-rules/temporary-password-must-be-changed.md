---
appliesTo:
- {type: journey, id: first-sign-in-with-temporary-password}
- {type: entity, id: family-member, facts: [Must change password]}
references:
- kind: code
  role: implementation
  target: src/routes/_app.tsx
---

# A temporary password must be replaced before anything else

A family member with a temporary password can only change it; every other page sends them back to their profile.

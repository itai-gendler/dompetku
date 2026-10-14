---
entities:
- {entity: profile, shows: [Username, Display name], collects: [Username, Display name, Password]}
- {entity: family-member, shows: [Must change password]}
- {entity: wallet-access, shows: [Level], collects: [Level]}
- {entity: account, shows: [Name, Archived]}
references:
- kind: code
  role: implementation
  target: src/components/users-card.tsx
---

# Family members

The owner and every family member, their status, and per account the access each member holds.

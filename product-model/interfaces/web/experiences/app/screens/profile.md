---
entities:
- {entity: profile, shows: [Username, Display name, Address, Profile photo], collects: [Display name, Address, Profile photo, Password]}
- {entity: family-member, shows: [Must change password]}
entryPoints:
- web: /profile
references:
- kind: code
  role: implementation
  target: src/routes/_app/profile.tsx
---

# Profile

Name, address, photo and password. A family member with a temporary password is held here until they choose their own.

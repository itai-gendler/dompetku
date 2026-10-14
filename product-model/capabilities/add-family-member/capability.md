---
domain: settings
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts
- kind: code
  role: implementation
  target: src/components/users-card.tsx
---

# Add family member

The owner adds a family member with a username (3–32 lower-case letters, digits, dots, underscores or dashes, never changed afterwards), an optional full name and a temporary password. The new member has no wallet access yet.

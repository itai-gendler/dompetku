---
entities:
- {entity: profile, collects: [Username, Password]}
entryPoints:
- web: /login
references:
- kind: code
  role: implementation
  target: src/routes/login.tsx
---

# Sign in

Username and password, then a six-digit code when two-step sign-in is on.

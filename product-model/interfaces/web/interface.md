---
type: web
actors: [owner, family-member]
entryPoints:
- web: /login
- web: /dashboard
references:
- kind: code
  role: implementation
  target: src/routes/_app.tsx
- kind: code
  role: implementation
  target: src/lib/server-fn-access.ts#SERVER_FN_ACCESS
---

# Web app

The browser app, installable on a phone or desktop. Every page is in Indonesian or English, switchable at any time.

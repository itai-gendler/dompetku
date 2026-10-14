---
availability:
- place: web::public
references:
- kind: code
  role: implementation
  target: src/lib/auth.functions.ts#login
- kind: code
  role: implementation
  target: src/lib/login-throttle.ts#isLoginLocked
- kind: code
  role: implementation
  target: src/lib/totp.server.ts
---

# Sign in

Sign in to the web app with a username and password. The owner's credentials come from the deployment's configuration until the owner chooses a password in the app; a family member has their own. When two-step sign-in is on, the owner also enters a code from an authenticator app.

---
kind: configuration
of: capability-scenario
takesEffect: When the owner signs in. Setting or clearing the secret in the deployment's configuration applies to the next sign-in.
stability: Sessions already open stay open when two-step sign-in is switched on or off; a pending code request expires after five minutes.
alternatives:
- id: sign-in-with-password
  selectedWhen: The deployment sets no valid two-step secret (APP_TOTP_SECRET), or it is a demo instance. Missing or invalid secret means password only.
- id: sign-in-with-password-and-code
  selectedWhen: The deployment sets a valid two-step secret and it is not a demo instance. Only the owner is asked for a code; family members always sign in with a password alone.
references:
- kind: code
  role: implementation
  target: src/lib/totp.server.ts
- kind: code
  role: implementation
  target: src/components/two-factor-card.tsx
---

# Two-step sign-in

The owner can add an authenticator code to signing in; both the password-only and the two-step sign-in are supported, chosen by the deployment.

---
kind: person
acts: external
relations:
- {entity: profile, verb: signs in as, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#ROLE_CAPABILITIES
- kind: code
  role: implementation
  target: src/lib/users.server.ts#resolvePrincipal
---

# Owner

The person whose login is defined in the deployment's configuration. The owner has every permission, is never changed or removed from the web app, and is the one the Telegram bot and the automation API act for.

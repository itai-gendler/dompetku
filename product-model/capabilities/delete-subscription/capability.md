---
domain: subscriptions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/subscriptions.tsx
- kind: code
  role: implementation
  target: src/lib/schemas.ts#subscriptionSchema
---

# Delete subscription

The owner deletes a subscription; past payments stay.

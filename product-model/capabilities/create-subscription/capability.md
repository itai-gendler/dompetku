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

# Create subscription

The owner adds a subscription with its price, optional tax, cycle and next bill.

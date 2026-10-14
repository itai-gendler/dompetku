---
entities:
- {entity: subscription, shows: [Name, Amount, Tax percent, Currency, Cycle, Interval, Next due date, Active], collects: [Name, Amount, Tax percent, Currency, Cycle, Interval, Next due date, Active, Notes]}
entryPoints:
- web: /subscriptions
references:
- kind: code
  role: implementation
  target: src/routes/_app/subscriptions.tsx
---

# Subscriptions

Subscriptions with their price including tax, next bill and the monthly and yearly equivalent.

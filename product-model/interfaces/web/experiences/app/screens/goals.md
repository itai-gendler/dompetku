---
entities:
- {entity: goal, shows: [Name, Target amount, Saved amount, Deadline, Projection], collects: [Name, Target amount, Saved amount, Deadline, Color]}
- {entity: account, shows: [Name]}
entryPoints:
- web: /goals
references:
- kind: code
  role: implementation
  target: src/routes/_app/goals.tsx
---

# Goals

Savings goals with progress, deadline, what to put aside per month and week, and the estimated completion month.

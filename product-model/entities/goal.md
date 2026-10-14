---
domain: goals
references:
- kind: code
  role: implementation
  target: src/lib/goals.ts#projectGoal
- kind: code
  role: implementation
  target: src/lib/schemas.ts#goalSchema
---

# Goal

A savings goal, optionally tied to the savings account the money is kept in.

## Information kept

- **Name** — for example Dana darurat
- **Target amount** — the amount to reach, in IDR
- **Saved amount** — what has been put aside so far
- **Deadline** — an optional date
- **Color** — a display color
- **Projection** — the monthly and weekly amount needed before the deadline, whether the goal is on track or behind, and the estimated completion month at the pace so far

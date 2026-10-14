---
domain: subscriptions
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#subscriptionSchema
- kind: code
  role: implementation
  target: src/lib/subscriptions.ts
---

# Subscription

A bill paid every month or year, or every few of them, such as Netflix.

## Information kept

- **Name** — for example Netflix
- **Amount** — the price before tax
- **Tax percent** — optional tax added on payment
- **Currency** — IDR or USD
- **Cycle** — monthly or yearly
- **Interval** — every how many cycles, 1 to 36
- **Next due date** — the next bill
- **Active** — only active subscriptions are listed as bills and reminders
- **Notes** — free text

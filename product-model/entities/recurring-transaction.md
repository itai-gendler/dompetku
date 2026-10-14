---
domain: recurring-transactions
relations:
- {entity: transaction, verb: posts, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: src/lib/recurring.ts
- kind: code
  role: implementation
  target: src/lib/schemas.ts#recurringSchema
---

# Recurring transaction

A schedule for an income, expense or transfer that repeats, such as salary or rent. An automatic one is posted when due; a manual one shows up in the reminders to be recorded.

## Information kept

- **Name** — for example Gaji
- **Kind** — income, expense or transfer
- **Amount** — the amount of each occurrence
- **Currency** — IDR or USD
- **Cycle** — weekly, monthly or yearly
- **Interval** — every how many cycles, 1 to 36
- **Day of month** — the anchor day for monthly and yearly schedules; past the month's end it falls on the last day
- **Start date** — the first day the schedule can fall on
- **Next due date** — the next occurrence
- **End date** — an optional last day
- **Auto-post** — whether occurrences are recorded automatically when due
- **Description** — the description given to each posted transaction
- **Merchant** — the merchant given to each posted transaction

## States

### Active

Occurrences come due.

### Paused

Nothing comes due; the owner paused it or its end date has passed.

---
domain: debts
relations:
- {entity: installment-payment, verb: is repaid by, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: src/lib/schemas.ts#debtSchema
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeDebts
---

# Debt

A paylater, loan, credit card or personal debt repaid in a fixed number of monthly installments.

## Information kept

- **Name** — for example Kredivo HP
- **Provider** — the lender
- **Kind** — paylater, loan, credit card, personal or other
- **Currency** — IDR or USD
- **Total amount** — the amount borrowed
- **Installment amount** — the amount of each monthly installment
- **Number of installments** — 1 to 600
- **First installment month** — the month the first installment falls in
- **Due day** — the day of the month an installment is due
- **Interest rate** — an optional percentage
- **Notes** — free text
- **Next due date** — the due date of the next unpaid installment
- **Remaining amount** — unpaid installments times the installment amount

## States

### Active

Installments are still due.

### Paid off

Every installment is paid.

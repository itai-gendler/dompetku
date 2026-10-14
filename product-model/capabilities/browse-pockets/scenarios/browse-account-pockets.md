---
kind: primary
routes:
  r: Web
steps:
- text: The Family member reads each Pocket of an Account shared with them
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: [Name, Balance]}
  - {entity: pocket, effect: reads, facts: [Name, Allocated amount, Remaining, Low-balance threshold, Period]}
  contexts:
    r:
      place: web::app::account-detail
---

# See an account's pockets

## Trigger

Someone who may see an account opens its page.

## Outcome

Each pocket shows allocated and remaining amounts and a low or empty badge, with the account's unallocated figure.

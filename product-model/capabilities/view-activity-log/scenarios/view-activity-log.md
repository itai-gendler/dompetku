---
kind: primary
routes:
  r: Web
steps:
- text: The Owner reads each Activity entry
  kind: actor
  actor: owner
  entities:
  - {entity: activity-entry, effect: reads, facts: [Action, Actor, Detail, Time]}
  contexts:
    r:
      place: web::administration::activity-log
---

# Read the activity log

## Trigger

The owner opens the activity log in Settings.

## Outcome

The latest entries are listed newest first.

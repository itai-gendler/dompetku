---
kind: validation
routes:
  r: Web
steps:
- text: The Owner picks a file that is not a backup
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::backup
- text: The Product refuses the file
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::backup
---

# The file is not a backup

## Trigger

The file is larger than 20 MB or is not a Dompetku backup.

## Outcome

Nothing is restored and the owner is told why.

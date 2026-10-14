---
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#changePassword
- kind: code
  role: implementation
  target: src/lib/password.ts#passwordProblems
---

# Change password

Change one's own password from the profile page. The new password has at least 10 characters, does not start or end with a space and is not the username. Every other session of that person ends; this device stays signed in.

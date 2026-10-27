---
"@effect/sql-pg": patch
---

Fix releasing a pinned connection sometimes closing a healthy session when a just-closed `listen` scope's `UNLISTEN` was already running. The release now waits for that `UNLISTEN` to finish, and still closes the session if a statement, stream, or listener is left running.

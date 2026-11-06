# Engineering choices

- Durable request capture precedes workflow serialization, preventing lost Power Automate attachments when pending jobs are replaced.
- A single manifest pins both feed files with hashes; consumers verify the exact commit rather than racing latest heads.
- Parser and blind visual extraction provide independent work-schedule evidence.
- All-calendar discovery keeps new calendars such as Georgia Winterguard in the scheduling constraints.
- Preferences and workout templates are editable files, separate from scheduling code.
- Study is allocated first; maintenance and gym are coordinated within one availability snapshot.
- Deterministic safety checks and a required intelligent review serve different purposes.
- ETags, scoped ownership markers, create-before-delete ordering and an operation journal make partial failures recoverable.
- No extra hosted service or database is needed for one user.

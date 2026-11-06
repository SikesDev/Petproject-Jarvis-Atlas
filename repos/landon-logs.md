# Landon Logs

Private cloud planning and calendar ownership.

- `preferences/` holds current prose, numeric scheduling rules and workout templates.
- `landon_scheduler/` separates preferences, calendar codecs, CalDAV snapshots, planning, review, storage and reconciliation.
- `scripts/schedule.py` is the sole production entry point.
- `data/scheduler/` holds current outcome and recovery evidence.
- The small stdio MCP bridge reads status/preferences and reports the disabled future appointment integration.

Study blocks go to School, gym to Personal and flexible maintenance to Planner. No local-app reminder integration is part of this architecture.

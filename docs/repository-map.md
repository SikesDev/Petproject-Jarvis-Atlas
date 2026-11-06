# Repository map

| Repository | Ownership | Runtime relationship |
|---|---|---|
| work-school-automation-hub | Private ingestion, task/work feeds, input receipts and snapshot manifest | Sends one pinned feed-ready event to Landon-Logs |
| Landon-Logs | Preferences, school-first coordinated planning, review and owned iCloud writes | Reads the exact feed snapshot and all current calendars |
| API-Interface | Static PWA shell for later development | No active link to personal repositories or calendar APIs |
| Petproject-Jarvis-Atlas | Architecture narrative and synthetic examples | Documentation only; no runtime imports |

Gas City/work-graph samples are historical examples of a separate coordination tool, not a dependency of the current cloud pipeline. Its archive and coordinator are not supplied by these repositories.

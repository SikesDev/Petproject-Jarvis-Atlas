# Current architecture

```mermaid
flowchart TD
  Canvas[Authenticated Canvas calendar URL] --> Capture[Private ingestion repository]
  Power[Power Automate attachment and dispatch] --> Inbox[Durable Actions artifact inbox]
  Inbox --> Capture
  Capture --> Parser[Source-specific parser]
  Parser --> Review[Free GitHub Models review and independent vision]
  Review -->|unresolved only| Paid[OpenAI last resort]
  Review --> Feeds[Canvas task ICS and Work ICS]
  Paid --> Feeds
  Feeds --> Manifest[One hash-validated manifest at exact Git commit]
  Manifest --> Planner[Private coordinated cloud scheduler]
  Preferences[Editable preferences folder] --> Planner
  Calendars[All current iCloud calendars] --> Planner
  Planner --> Gate[Hard constraints and intelligent preference review]
  Gate --> Journal[ETag reconciliation and recovery journal]
  Journal --> School[School: study]
  Journal --> Personal[Personal: gym]
  Journal --> Maintenance[Planner: flexible maintenance]
  Shell[Static PWA shell: future only]
```

The repositories exchange versioned files and a single repository dispatch. They do not require a database server, message broker, paid hosting platform or extra identity system. Existing Georgia Tech/Power Automate/GitHub/iCloud authentication is preserved. Tailscale remains the network boundary for a future locally hosted interface.

The scheduler owns only marked generated events in the active window. Human-created calendar events, subscriptions and legacy records are preserved. Appointments are a disabled future integration. Actual iCloud events define commitments, including Georgia Winterguard; no summer class timetable is hard-coded.

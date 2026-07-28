# Workflow Walkthroughs

## Canvas Calendar Filtering

```mermaid
sequenceDiagram
    participant Feed as Canvas-like ICS Feed
    participant Parser as Deterministic Filter
    participant Cache as Review Cache
    participant Model as Model Review
    participant Output as Filtered ICS

    Feed->>Parser: Raw calendar events
    Parser->>Parser: Unfold lines, split events, remove noisy records
    Parser->>Cache: Check known event decisions
    Cache-->>Parser: Reuse prior decisions
    Parser->>Model: Send only unresolved current/future decisions
    Model-->>Parser: Structured keep/drop guidance
    Parser->>Output: Publish clean assignment calendar
```

See [synthetic raw calendar](../samples/canvas/raw-calendar.ics) and [synthetic filtered calendar](../samples/canvas/filtered-calendar.ics).

## Work Schedule Extraction

```mermaid
flowchart TB
    Doc["Schedule document\nDOCX, PDF, HTML, or image"]
    Deterministic["Parser\ntext conversion, table/cell extraction,\ntime normalization"]
    Model["Independent model extraction"]
    Compare["Normalize and compare rows"]
    Arbiter["Vision fallback for disagreements"]
    Calendar["Work schedule ICS"]
    Issue["Validation issue or proposal"]

    Doc --> Deterministic
    Doc --> Model
    Deterministic --> Compare
    Model --> Compare
    Compare -->|"matching rows"| Calendar
    Compare -->|"disputed rows"| Arbiter
    Arbiter -->|"resolved"| Calendar
    Arbiter -->|"needs human review"| Issue
```

See [synthetic input rows](../samples/work-schedule/input-shifts.json) and [synthetic calendar output](../samples/work-schedule/work-schedule.ics).

## Daily Startup

```mermaid
flowchart LR
    Supervisor["Supervisor session"]
    MCP["Landon Logs MCP server"]
    Feeds["School, work, and agent feeds"]
    Workers["Scoped workers"]
    Summary["Daily welcome summary"]
    Decisions["User decisions"]

    Supervisor --> MCP
    MCP --> Feeds
    MCP --> Workers
    Workers --> MCP
    MCP --> Summary
    Summary --> Decisions
```

See [synthetic daily startup payload](../samples/agent/daily-startup.json).

## Interface Bootstrap

```mermaid
sequenceDiagram
    participant Browser as PWA Browser
    participant API as Local API
    participant Private as Private Agent Repo
    participant Public as Public Feed Repo
    participant Store as Interface Store

    Browser->>API: GET /api/bootstrap
    API->>Private: Read daily state, plans, approvals
    API->>Public: Read feed freshness and today events
    API->>Store: Read local chat and decisions
    API-->>Browser: Dashboard payload
```

See [synthetic bootstrap response](../samples/interface/bootstrap-response.json).


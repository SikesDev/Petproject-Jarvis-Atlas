# Calendar Filtering Snippets

These excerpts show structure-only logic from the calendar pipeline.

## Remove Rich Descriptions From Published Events

```python
def sanitize_event(event):
    sanitized = []
    for line in event:
        if line.startswith("DESCRIPTION") or line.startswith("X-ALT-DESC"):
            continue
        sanitized.append(line)
    return sanitized
```

## Keep Actionable Events After Duplicate Checks

```python
def filter_calendar(text, start_date=None):
    lines = unfold_ics(text)
    header, events, footer = split_calendar(lines)
    platform_keys = platform_assignment_keys(events)
    kept_events = []

    for event in events:
        starts_on = event_date(event)
        if start_date and starts_on and starts_on < start_date:
            continue
        if should_keep_event(event, platform_keys):
            kept_events.append(sanitize_event(event))

    return write_calendar(header, kept_events, footer)
```


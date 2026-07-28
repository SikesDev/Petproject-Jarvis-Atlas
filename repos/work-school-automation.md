# Work + School Automation

## Role

Public ingestion and publication edge for school and work calendar automation.

## What It Does

- Filters a Canvas-like ICS feed into a cleaner actionable calendar.
- Parses work schedule documents into normalized shift rows.
- Publishes generated ICS feeds.
- Uses GitHub Actions for recurring cloud execution.
- Uses model review as a validation layer around deterministic parsing.
- Keeps local reminder sync narrow and macOS-specific.

## Notable Source Areas

| Area | Purpose |
| --- | --- |
| `filter_canvas_ics.py` | ICS parsing, event filtering, line folding, and output feed generation |
| `work_schedule_ics.py` | Schedule document parsing, date/time normalization, and ICS writing |
| `canvas_cloud_sync.py` | Cloud orchestration for Canvas feed updates |
| `work_schedule_cloud_sync.py` | Cloud orchestration for work schedule extraction and review |
| `model_review.py` | Shared model-provider plumbing without feed-specific business rules |
| `.github/workflows/` | Scheduled and dispatchable automation |

## Engineering Takeaway

This repo keeps the public edge deterministic. It parses known input formats directly, then uses model review only for cases that benefit from independent judgment or fallback arbitration.

## Related Samples

- [Raw calendar sample](../samples/canvas/raw-calendar.ics)
- [Filtered calendar sample](../samples/canvas/filtered-calendar.ics)
- [Synthetic shift rows](../samples/work-schedule/input-shifts.json)
- [Synthetic work schedule ICS](../samples/work-schedule/work-schedule.ics)


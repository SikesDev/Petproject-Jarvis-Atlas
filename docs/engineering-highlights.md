# Engineering Highlights

## Deterministic Parsing Before AI Review

The calendar and schedule pipelines parse known formats directly, normalize rows, and only call model review for ambiguous or disputed cases. This keeps the system cheaper, easier to test, and easier to reason about.

Example areas:

- ICS unfolding/folding and event filtering.
- HTML/PDF schedule cell extraction.
- Date, time, and role normalization.
- Parser/model comparison before fallback arbitration.

## Policy-Gated Private Agent Layer

The private agent repository uses a local MCP server to expose safe tools to a supervising session. Small worker agents produce structured reports, while the supervisor is responsible for consolidating context and asking for approval before high-impact work.

Example areas:

- Daily startup summaries.
- Feed freshness checks.
- Worker report registry.
- iCloud and calendar access policy.
- Agent-owned calendar writes.

## Thin PWA Control Plane

The Jarvis Interface repo deliberately avoids becoming the decision authority. It provides a cross-device dashboard and records user intent, then leaves execution to private-owned contracts.

Example areas:

- Same-origin Node API.
- Static PWA shell.
- Local interface state.
- Read-only adapters to adjacent repos.
- Approval and chat routes that record state until the private layer owns execution.

## Public Examples From Private Systems

The atlas uses synthetic files that preserve data shape without copying production content. These examples are useful for demos, documentation, tests, and future public-hosted writeups.

Representative samples:

- [Canvas raw and filtered ICS](../samples/canvas)
- [Work schedule rows and ICS](../samples/work-schedule)
- [Daily startup summary](../samples/agent/daily-startup.json)
- [Interface bootstrap payload](../samples/interface/bootstrap-response.json)
- [Gas City JSONL work graph](../samples/gas-city/work-items.jsonl)

## Code Excerpts

Short, structure-focused snippets are collected in [Snippets](../snippets). They are intentionally selected to show patterns rather than private constants, records, URLs, or environment details.


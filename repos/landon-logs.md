# Landon Logs

## Role

Private cognition, policy, memory, MCP bridge, and agent-owned scheduling layer.

## What It Does

- Provides a local stdio MCP server for supervising agent sessions.
- Reads public feed outputs from Work + School Automation.
- Stores private policies, preferences, proposals, worker reports, and agent calendar state.
- Produces daily startup summaries from feed freshness, itinerary, and private planning context.
- Dispatches small scoped workers for feed monitoring, task inventory, memory review, assignment triage, and planning notes.
- Keeps high-impact calendar, memory, and external-service actions behind policy and user intent.

## Notable Source Areas

| Area | Purpose |
| --- | --- |
| `mcp_landon_logs.py` | Standard-library MCP server and local tool surface |
| `agent_framework/` | Shared parsing and agent helper logic |
| `agents/` | Worker registry, schemas, and prompts |
| `policies/` | Access and automation boundaries |
| `scripts/` | Planning, schedule review, reminders, and context extraction helpers |
| `landon_logs/` | Durable human-readable knowledge surfaces |

## Engineering Takeaway

This repo is the private authority layer. It centralizes memory and policy while allowing other repos to stay narrow: public feed publication remains outside, and UI state is rendered through controlled adapters.

## Related Samples

- [Synthetic daily startup payload](../samples/agent/daily-startup.json)
- [Gas City synthetic work items](../samples/gas-city/work-items.jsonl)


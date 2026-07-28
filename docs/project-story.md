# Project Story

Petproject Jarvis is a personal automation platform built as a set of small, local-first systems instead of a single monolith.

The first layer turns noisy external calendars and work schedules into clean feeds. The second layer keeps private memory, policy, and planning state behind a local MCP server. The third layer is a lightweight PWA control surface that can show the current day, approvals, activity, chat, and finance snapshots from a trusted local machine.

The interesting engineering challenge is not just "make an assistant." It is designing boundaries so the assistant can be useful without owning every source of truth. Calendar ingestion, private planning, local approvals, and browser-facing UX all have separate responsibilities.

This atlas is the public companion repository. It documents the architecture and workflows with synthetic examples so the project can be shared publicly while the actual private repos stay private.

## What This Demonstrates

- Multi-repo system design.
- Local-first automation around real personal workflows.
- Privacy-aware documentation and demo data.
- Deterministic parsers with model-backed review gates.
- MCP-based agent supervision.
- A thin PWA interface over private state.
- Work graph tracking through Gas City JSONL archives.


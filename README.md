# Petproject Jarvis Atlas

Public-facing atlas for a private automation workspace.

This repository explains the architecture, workflows, and engineering patterns behind a personal Jarvis-style automation system without publishing the private source repositories or their production data. It is meant to be readable as a portfolio project: enough implementation detail to show how the system is built, with synthetic examples where real records would be private.

## What It Covers

The atlas describes four local Git repositories and worktrees from the Gas City workspace:

| Project | Role | Source Shape |
| --- | --- | --- |
| Work + School Automation | Public ingestion and calendar publication edge | Python parsers, GitHub Actions, generated ICS feeds |
| Landon Logs | Private agent memory, policy, MCP bridge, and scheduling layer | Python MCP server, policy JSON, worker reports, agent-owned calendar state |
| Jarvis Interface | Thin web control surface for dashboard, chat, approvals, activity, and finance snapshots | Dependency-light Node/PWA app |
| Gas City JSONL Archive | Local issue/work-item persistence layer | JSONL archives for work, comments, labels, metadata, and dependencies |

## Portfolio Highlights

- Converts messy external inputs into normalized calendar feeds with deterministic parsers and model-backed review.
- Separates public ingestion, private planning, and user-facing interface boundaries.
- Uses policy-gated agent workflows where small workers report facts and a supervising agent consolidates decisions.
- Keeps the web interface thin: it renders state, records local actions, and waits for private-owned execution contracts.
- Provides synthetic samples for calendar filtering, work schedule extraction, daily startup summaries, approvals, and dashboard bootstrap payloads.

## Start Here

- [Repository Map](docs/repository-map.md)
- [System Architecture](docs/architecture.md)
- [Workflow Walkthroughs](docs/workflows.md)
- [Engineering Highlights](docs/engineering-highlights.md)
- [Project Story](docs/project-story.md)

## Visuals

- [System map SVG](assets/system-map.svg)
- Mermaid workflow diagrams are embedded in [Workflow Walkthroughs](docs/workflows.md).

## Synthetic Samples

The `samples/` directory contains fictional data that demonstrates the same data shapes and workflows used by the real system:

- Canvas-like calendar filtering
- Work-schedule normalization
- Agent daily startup payloads
- Dashboard bootstrap responses
- Gas City work-item archives
- Finance dashboard snapshots

No real production calendars, credentials, personal records, finance records, browser state, or private remotes are included.


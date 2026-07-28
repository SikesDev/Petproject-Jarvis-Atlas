# Jarvis Interface

## Role

Thin browser-based control surface for the private agent system.

## What It Does

- Serves a dependency-light PWA shell.
- Provides a same-origin local API.
- Reads dashboard state from adjacent private and public repos.
- Shows Today, chat, approvals, activity, device readiness, and finance snapshot views.
- Stores interface-local chat messages, approval decisions, push subscriptions, and optional finance snapshots.
- Keeps secrets and linked finance tokens server-side.

## Notable Source Areas

| Area | Purpose |
| --- | --- |
| `src/` | Static PWA shell, responsive UI, service worker, and manifest |
| `server/routes/api.mjs` | Local API routes for dashboard, chat, approvals, activity, finance, and push setup |
| `server/adapters/` | Read-only adapters for private agent state, public feed state, and finance provider data |
| `server/store/` | Interface-local JSON state |
| `scripts/` | Build, dev server, doctor, healthcheck, and launchd plist helpers |
| `docs/` | Architecture and deployment notes |

## Engineering Takeaway

The interface is useful because it refuses to become the system brain. It renders, records, and routes intent while leaving durable policy and execution ownership in the private layer.

## Related Samples

- [Synthetic bootstrap payload](../samples/interface/bootstrap-response.json)
- [Synthetic finance snapshot](../samples/finance/finance-snapshot.json)


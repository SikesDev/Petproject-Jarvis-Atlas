# Gas City JSONL Archive

## Role

Local archive of Gas City work graph state.

## What It Does

- Stores project-scoped JSONL records.
- Tracks issues, comments, dependencies, labels, config, and metadata.
- Gives the workspace a compact append-friendly history surface.
- Supports multi-repo coordination without exposing private source content in this atlas.

## Source Shape

The archive is grouped by project key. Each project has JSONL files for work items, comments, labels, dependencies, configuration, and metadata.

## Engineering Takeaway

The archive makes local agent work more traceable. It separates coordination metadata from the source repos themselves, which lets agents inspect and route work without requiring every repository to expose its private contents.

## Related Samples

- [Synthetic work items](../samples/gas-city/work-items.jsonl)


# MCP Boundary Snippets

## Redact Secret-Like Config Values

```python
def redacted_config(config):
    cleaned = json.loads(json.dumps(config))
    secrets = cleaned.setdefault("secrets", {})
    for key in list(secrets):
        if "password" in key or "token" in key:
            secrets[key] = "<redacted>"
    return cleaned
```

## Skip Pulls When Tracked Local Work Exists

```python
def tracked_worktree_dirty(status_text):
    for line in status_text.splitlines():
        if not line.strip():
            continue
        if line.startswith("??"):
            continue
        return True
    return False
```


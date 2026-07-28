# Interface API Snippets

## Combine Agenda Items Without Duplicates

```javascript
function combineAgenda(privateEvents, publicEvents) {
  const seen = new Set();
  const rows = [];

  for (const item of [...privateEvents, ...publicEvents]) {
    const key = `${item.title}|${item.start}|${item.end}`;
    if (seen.has(key)) {
      continue;
    }
    seen.add(key);
    rows.push(item);
  }

  return rows.sort((a, b) => String(a.start || "").localeCompare(String(b.start || "")));
}
```

## Approval Route Shape

```javascript
async function recordApprovalDecision(id, body) {
  if (!["Approved", "Denied"].includes(body.decision)) {
    return { status: 400, error: "invalid_decision" };
  }

  const entry = await store.recordApprovalDecision(id, body.decision, body);
  return {
    ok: true,
    decision: entry,
    execution: {
      status: "recorded_only",
      next: "Delegate execution to the private policy layer."
    }
  };
}
```


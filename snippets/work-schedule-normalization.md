# Work Schedule Normalization Snippets

## Normalize Text Before Parsing

```python
def normalize_text(value):
    value = unicodedata.normalize("NFKC", value)
    value = value.replace("\xa0", " ")
    value = "".join(
        " " if char.isspace() else char
        for char in value
        if char.isspace() or unicodedata.category(char) not in {"Cc", "Cf"}
    )
    value = re.sub(r"\s+", " ", value)
    return value.strip()
```

## Convert Shifts Into Comparable Rows

```python
def normalized_shift_rows(shifts):
    return [
        {
            "date": shift.date.isoformat(),
            "start": shift.start.strftime("%H:%M"),
            "end": shift.end.strftime("%H:%M"),
            "role": normalize_role(shift.role),
        }
        for shift in sorted(shifts, key=lambda item: (item.start, item.end, item.role))
    ]
```


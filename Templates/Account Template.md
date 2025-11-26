---
type:
  - Account
status:
  - Active
parent:
project:
account:
area:
  -
priority:
  -
due:
created: "{{date}}"
tags: []
---

## Overview

Brief description of the account/context.

## Vision

Where is this heading?

## Key Metrics

| Metric | Current | Target |
|--------|---------|--------|
|        |         |        |

## Active Goals

```dataview
LIST
FROM "Items"
WHERE account = this.file.link AND type = "Goal" AND status = "Active"
```

## Notes


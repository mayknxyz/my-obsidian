---
type:
  - Epic
status:
  - Inbox
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

What feature or capability does this epic deliver?

## Acceptance Criteria

- [ ]
- [ ]
- [ ]

## Dependencies

| Dependency | Type | Status |
|------------|------|--------|
|            | Blocks / Blocked by |   |

## Technical Considerations

-

## Stories

```dataview
TABLE status, priority
FROM "Items"
WHERE parent = this.file.link AND type = "Story"
SORT priority ASC
```

## Notes


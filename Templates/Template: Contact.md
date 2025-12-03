---
type:
  - Contact
status:
  - Active
parent:
project:
account:
dept:
  -
context:
  -
priority:
  -
due:
created: "{{date}}"
email:
phone:
company:
role:
linkedin:
location:
tags: []
---

## Context

How do we know this person? What's the relationship?

## Interactions

```dataview
TABLE date, summary
FROM "Items"
WHERE type = "Meeting" AND contains(attendees, this.file.link)
SORT date DESC
LIMIT 5
```

## Notes


---
type:
  - Contact
status:
  - Active
parent:
project:
account: "[[Personal]]"
area:
  -
priority:
  -
due:
created: "2025-11-26"
email: john.doe@example.com
phone: "+1 555-0123"
company: Acme Corp
role: Senior Developer
linkedin: https://linkedin.com/in/johndoe
location: San Francisco, CA
tags: []
---

## Context

Met John at a tech meetup in SF. He's interested in beta testing the platform and has experience with similar tools.

## Interactions

```dataview
TABLE date, summary
FROM "Items"
WHERE type = "Meeting" AND contains(attendees, this.file.link)
SORT date DESC
LIMIT 5
```

## Notes

- Strong TypeScript background
- Works on developer tools at Acme
- Potential advisor or early adopter

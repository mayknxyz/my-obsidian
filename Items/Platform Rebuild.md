---
type:
  - Project
status:
  - Active
parent: "[[Launch MVP by Q2]]"
project:
account: "[[Personal]]"
area:
  - Dev
priority:
  - P1
due: 2025-03-31
created: "2025-11-26"
tags: []
---

## Overview

Rebuild the platform from scratch using modern tech stack (Next.js, Supabase, Tailwind). Focus on simplicity and speed.

## Scope

### In Scope

- User authentication (email, OAuth)
- Dashboard with key metrics
- RESTful API for integrations
- Basic billing integration

### Out of Scope

- Mobile app (phase 2)
- Advanced analytics (phase 2)
- White-labeling

## Success Criteria

- [ ] All core features functional
- [ ] 99% uptime
- [ ] Page load < 2 seconds

## Key Dates

| Milestone | Date | Status |
|-----------|------|--------|
| Kickoff   | 2025-11-26 | Done |
| Auth MVP  | 2025-12-15 | In Progress |
| Launch    | 2025-03-31 | Planned |

## Stakeholders

| Role | Person |
|------|--------|
| Owner | Mike |
| Dev   | Mike |

## Epics

```dataview
TABLE status, priority
FROM "Items"
WHERE project = this.file.link AND type = "Epic"
SORT priority ASC
```

## Risks & Dependencies

| Risk/Dependency | Impact | Mitigation |
|-----------------|--------|------------|
| Solo developer | High | Focus on MVP scope |
| Supabase limits | Medium | Monitor usage |

## Notes

Tech stack decision: Next.js for SSR/SEO, Supabase for quick backend, Tailwind for rapid UI.

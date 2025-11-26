---
type:
  - Epic
status:
  - Active
parent: "[[Platform Rebuild]]"
project: "[[Platform Rebuild]]"
account: "[[Personal]]"
area:
  - Dev
priority:
  - P1
due: 2025-12-15
created: 2025-11-26
tags: []
---

## Overview

Complete authentication system supporting email/password and OAuth providers (Google, GitHub).

## Acceptance Criteria

- [ ] Users can sign up with email/password
- [ ] Users can sign in with Google OAuth
- [ ] Users can sign in with GitHub OAuth
- [ ] Password reset flow works
- [ ] Sessions persist correctly

## Dependencies

| Dependency | Type | Status |
|------------|------|--------|
| Supabase Auth | External | Ready |
| OAuth app configs | Blocks | Done |

## Technical Considerations

- Use Supabase Auth for all auth flows
- Store minimal user data (id, email, name, avatar)
- JWT tokens with 1-hour expiry, refresh tokens for 7 days

## Stories

```dataview
TABLE status, priority
FROM "Items"
WHERE parent = this.file.link AND type = "Story"
SORT priority ASC
```

## Notes

Supabase handles most of the heavy lifting here. Focus on UX.

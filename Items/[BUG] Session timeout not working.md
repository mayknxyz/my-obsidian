---
type:
  - Bug
status:
  - Inbox
parent: "[[User Login Flow]]"
project: "[[Platform Rebuild]]"
account: "[[Personal]]"
area:
  - Dev
priority:
  - P2
due: 2025-11-27
created: 2025-11-26
tags: []
---

## Summary

Users are not being logged out after the expected session timeout period. Sessions persist indefinitely.

## Steps to Reproduce

1. Log in to the application
2. Wait for session timeout (should be 1 hour)
3. Refresh the page
4. User is still logged in (expected: redirected to login)

## Expected Behavior

User should be logged out and redirected to login page after 1 hour of inactivity.

## Actual Behavior

User remains logged in indefinitely. Refresh tokens seem to auto-renew without limit.

## Notes

May need to implement custom session timeout logic on top of Supabase's token refresh.

---
type:
  - Documentation
status:
  - Active
parent:
project: "[[Platform Rebuild]]"
account: "[[Personal]]"
area:
  - Dev
priority:
  -
due:
created: "2025-11-26"
last_reviewed: "2025-11-26"
doc_type:
  - Technical
tags: []
---

## Overview

API reference documentation for the authentication endpoints.

## Audience

Developers integrating with the platform API.

---

## Content

### Authentication Endpoints

#### POST /api/auth/signup

Create a new user account.

**Request:**
```json
{
  "email": "user@example.com",
  "password": "securepassword123"
}
```

**Response:**
```json
{
  "user": {
    "id": "uuid",
    "email": "user@example.com"
  },
  "session": {
    "access_token": "jwt_token",
    "refresh_token": "refresh_token"
  }
}
```

#### POST /api/auth/login

Authenticate an existing user.

**Request:**
```json
{
  "email": "user@example.com",
  "password": "securepassword123"
}
```

**Response:** Same as signup.

#### POST /api/auth/logout

End the current session.

**Headers:** `Authorization: Bearer <access_token>`

**Response:** `204 No Content`

---

## Related

```dataview
LIST
FROM "Items"
WHERE type = "Documentation" AND project = this.project AND file.name != this.file.name
```

## Changelog

| Date | Change | Author |
|------|--------|--------|
| 2025-11-26 | Created | Mike |

# Obsidian Vault Architecture — Bases-First System

## Overview

A flat-file, property-driven system using Obsidian Bases for dynamic views. All items live in a single folder with relationships managed via frontmatter links.

---

## Folder Structure

```
Vault/
├── Bases/                  # Saved Base views
│   ├── Status/             # Status-based views (Inbox, Backlog, Active, Blocked, Done)
│   ├── Timeline/           # Date-based views (Overdue, Today, This Week, Upcoming, Someday)
│   └── Views/              # Type-based views (Ideas, Journal, Goals, Projects, etc.)
├── Items/                  # All typed items (flat) + Journal entries
├── Resources/              # Reference material, non-actionable
├── Templates/              # Item templates
└── REMINDERS.md            # Startup reminders (pinned tab)
```

---

## Templates

### Account Template

**Location:** `Templates/Account Template.md`

```markdown
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

```

---

### Goal Template

**Location:** `Templates/Goal Template.md`

```markdown
---
type:
  - Goal
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

## Objective

What are we trying to achieve?

## Key Results

- [ ] KR1:
- [ ] KR2:
- [ ] KR3:

## Success Criteria

How do we know we've achieved this goal?

## Review Cadence

- **Check-in:** Weekly / Bi-weekly / Monthly
- **Next Review:**

## Related Projects

```dataview
LIST
FROM "Items"
WHERE parent = this.file.link AND type = "Project"
```

## Notes

```

---

### Project Template

**Location:** `Templates/Project Template.md`

```markdown
---
type:
  - Project
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

What is this project about?

## Scope

### In Scope

-

### Out of Scope

-

## Success Criteria

- [ ]
- [ ]

## Key Dates

| Milestone | Date | Status |
|-----------|------|--------|
| Kickoff   |      |        |
| MVP       |      |        |
| Launch    |      |        |

## Stakeholders

| Role | Person |
|------|--------|
| Owner |       |
| Dev   |       |

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
|                 |        |            |

## Notes

```

---

### Epic Template

**Location:** `Templates/Epic Template.md`

```markdown
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

```

---

### Story Template

**Location:** `Templates/Story Template.md`

```markdown
---
type:
  - Story
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

## User Story

**As a** [user type]
**I want** [action]
**So that** [benefit]

## Acceptance Criteria

- [ ]
- [ ]
- [ ]

## Notes

```

---

### Task Template

**Location:** `Templates/Task Template.md`

```markdown
---
type:
  - Task
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

## Description

What needs to be done?

## Checklist

- [ ]
- [ ]

## Notes

```

---

### Bug Template

**Location:** `Templates/Bug Template.md`

```markdown
---
type:
  - Bug
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

## Summary

Brief description of the bug.

## Steps to Reproduce

1.
2.
3.

## Expected Behavior

What should happen?

## Actual Behavior

What actually happens?

## Notes

```

---

### Idea Template

**Location:** `Templates/Idea Template.md`

```markdown
---
type:
  - Idea
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

## Idea

What's the concept?

## Problem It Solves

Why does this matter?

## Potential Impact

- **Effort:** Low / Medium / High
- **Value:** Low / Medium / High

## Next Steps

What would it take to explore this further?

## Notes

```

---

### Contact Template

**Location:** `Templates/Contact Template.md`

```markdown
---
type:
  - Contact
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

```

---

### Meeting Template

**Location:** `Templates/Meeting Template.md`

```markdown
---
type:
  - Meeting
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
date: "{{date}}"
attendees: []
created: "{{date}}"
tags: []
---

## Info

| Field     | Value |
|-----------|-------|
| Date      | {{date}} |
| Time      |       |
| Duration  |       |
| Location  |       |

## Attendees

-

## Agenda

1.
2.
3.

## Notes

### Discussion

-

### Decisions

-

## Action Items

- [ ] @person: Task — Due:
- [ ] @person: Task — Due:

## Follow-up

Next meeting:

```

---

### Documentation Template

**Location:** `Templates/Documentation Template.md`

```markdown
---
type:
  - Documentation
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
last_reviewed: "{{date}}"
doc_type:
  -
tags: []
---

## Overview

What does this document cover?

## Audience

Who is this documentation for?

---

## Content

*(Main documentation content goes here)*

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
| {{date}} | Created |        |

```

### Documentation Types

Use the `doc_type` property to categorize:

- **Technical:** API docs, architecture, code docs
- **Process:** How-tos, SOPs, workflows
- **Reference:** Specs, requirements, decisions (ADRs)
- **Guide:** Onboarding, tutorials, runbooks
- **Policy:** Internal policies, guidelines

---

### Journal Template

**Location:** `Templates/Journal Template.md`

The Journal template is used for quick capture of notes, ideas, and daily reflections. Journal entries are created via the Daily Notes plugin and stored in `Items/`.

```markdown
---
type:
  - Journal
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

# {{date}} {{time}}

## Focus

> What's the one thing that matters most today?

## Notes

-

## Ideas

-

## Log

-
```

### Journal vs Daily Notes

The Journal system replaces traditional daily notes:

| Aspect | Journal | Traditional Daily |
|--------|---------|-------------------|
| Location | `Items/` folder | Separate `Daily/` folder |
| Type | Has `type: Journal` property | No type property |
| Workflow | Goes through Inbox → Done flow | Static daily log |
| Views | Appears in Timeline Bases | Only in calendar view |
| Purpose | Quick capture, flexible notes | Structured daily review |

Journal entries are actionable items that flow through the status workflow, making them visible in Timeline Bases (Today, This Week, etc.).

---

## REMINDERS.md

**Location:** `REMINDERS.md` (vault root)

A plain markdown file for persistent reminders that opens automatically on startup via the `Main` workspace (pinned tab).

### Purpose

Unlike Items which flow through the status workflow (Inbox → Backlog → Active → Done), REMINDERS.md is for **persistent, always-visible content**:

- **Daily habits** — Recurring checklist items you review each day
- **Important rules** — Guidelines you should always follow
- **Don't forget** — Persistent reminders that don't fit the task workflow

### How It Works

1. The `Main` workspace (saved in `.obsidian/workspaces.json`) includes REMINDERS.md as a pinned tab
2. When you load the workspace, REMINDERS.md opens alongside your daily note
3. Pinned tabs persist across sessions

### Editing

Edit the file directly—no special syntax or properties required. Suggested structure:

```markdown
# Reminders

## Daily Habits
- [ ] Review calendar
- [ ] Check email

## Important Rules
- Always backup before major changes

## Don't Forget
- Weekly sync every Monday
```

### When to Use REMINDERS.md vs Items

| Use Case | Where |
|----------|-------|
| One-time task with deadline | Items/ (Task type) |
| Recurring habit/checklist | REMINDERS.md |
| Persistent rule/guideline | REMINDERS.md |
| Project-related work | Items/ (appropriate type) |
| Quick daily reminder | REMINDERS.md |

---

## Property Schema

| Property        | Type       | Values                                                                              | Purpose                          |
| --------------- | ---------- | ----------------------------------------------------------------------------------- | -------------------------------- |
| `type`          | List       | Account, Goal, Idea, Project, Epic, Story, Task, Bug, Contact, Meeting, Documentation, Journal | Item classification (dropdown)   |
| `status`        | List       | Inbox, Backlog, Active, Blocked, Waiting, Done, Archived                            | Workflow state (dropdown)        |
| `parent`        | Link       | `[[Item Name]]`                                                                     | Direct parent relationship       |
| `project`       | Link       | `[[Project Name]]`                                                                  | Root project (shortcut access)   |
| `account`       | Link       | `[[Account Name]]`                                                                  | Multi-account filtering          |
| `area`          | List       | Dev, Ops, Marketing, Sales, Finance, Admin                                          | Cross-cutting context (dropdown) |
| `priority`      | List       | P1, P2, P3                                                                          | Urgency/importance (dropdown)    |
| `due`           | Date       | YYYY-MM-DD                                                                          | Deadline                         |
| `created`       | Date       | YYYY-MM-DD                                                                          | Auto-filled on creation          |
| `tags`          | List       | Freeform                                                                            | Additional categorization        |
| `date`          | Date       | YYYY-MM-DD                                                                          | Meeting date (Meeting only)      |
| `attendees`     | List       | `[[Contact]]` links                                                                 | Meeting participants             |
| `last_reviewed` | Date       | YYYY-MM-DD                                                                          | Doc freshness (Documentation)    |
| `doc_type`      | List       | Technical, Process, Reference, Guide, Policy                                        | Documentation category           |
| `email`         | Text       | Email address                                                                       | Contact email (Contact only)     |
| `phone`         | Text       | Phone number                                                                        | Contact phone (Contact only)     |
| `company`       | Text       | Company name                                                                        | Contact company (Contact only)   |
| `role`          | Text       | Job title                                                                           | Contact role (Contact only)      |
| `linkedin`      | Text       | LinkedIn URL                                                                        | Contact LinkedIn (Contact only)  |
| `location`      | Text       | City/Country                                                                        | Contact location (Contact only)  |

### Property Type Examples

**List property (dropdown-enabled):**
```yaml
type:
  - Task
status:
  - Active
priority:
  - P1
area:
  - Dev
```

**Link property:**
```yaml
parent: "[[User Login Story]]"
project: "[[Platform Rebuild]]"
account: "[[Personal]]"
```

---

## Type Hierarchy

```
Account
└── Goal
    └── Project
        └── Epic
            └── Story
                └── Task / Bug
```

**Supporting Types (not hierarchical):**
- **Idea** — Parking lot for concepts
- **Journal** — Quick capture, daily notes
- **Contact** — People/CRM
- **Meeting** — Link to `project` or `parent` for context
- **Documentation** — Link to `project` or `parent` it documents

**Actionable Types** (shown in Timeline Bases):
- Task, Bug, Story, Epic, Project, Goal, Idea

### Linking Example

For a deeply nested Task:

```yaml
type:
  - Task
parent: "[[User Login Story]]"      # Direct parent (Story)
project: "[[Platform Rebuild]]"     # Root project (always set)
account: "[[Personal]]"
```

### Setting the `project` Property

| Item Type     | `parent`                  | `project`                  |
| ------------- | ------------------------- | -------------------------- |
| Project       | `[[Goal]]`                | *(leave empty or self)*    |
| Epic          | `[[Project]]`             | `[[Project]]`              |
| Story         | `[[Epic]]`                | `[[Project]]`              |
| Task          | `[[Story]]` or `[[Epic]]` | `[[Project]]`              |
| Bug           | `[[Story]]` or `[[Epic]]` | `[[Project]]`              |
| Meeting       | *(optional)*              | `[[Project]]` if relevant  |
| Documentation | *(optional)*              | `[[Project]]` if relevant  |
| Contact       | *(optional)*              | *(usually empty)*          |

**Rule:** Always inherit `project` from the root Project, regardless of depth.

---

## Bases Configuration

Bases are organized into three folders:

```
Bases/
├── Status/     # Status-based workflow views
├── Timeline/   # Date-based views (actionable items only)
└── Views/      # Type-based views
```

### Status/ — Workflow Views

| # | Base Name   | Filters                                | Use Case              |
|---|-------------|----------------------------------------|----------------------|
| 01 | **Inbox**   | `status == ["Inbox"]`                  | Triage new items      |
| 02 | **Backlog** | `status == ["Backlog"]`                | Triaged, not started  |
| 03 | **Active**  | `status == ["Active"]`                 | Daily focus           |
| 04 | **Blocked** | `status == ["Blocked"]` or `["Waiting"]` | Dependency tracking |
| 05 | **Done**    | `status == ["Done"]`                   | Archive/review        |

### Timeline/ — Date-Based Views

All Timeline Bases filter for **actionable types only**: Task, Bug, Story, Epic, Project, Goal, Idea.

| # | Base Name       | Filters                                      | Use Case                |
|---|-----------------|----------------------------------------------|-------------------------|
| 01 | **Overdue**     | `due < today()` + `status != Done`           | Past due items          |
| 02 | **Today**       | `due == today()` + `status != Done`          | Today's focus           |
| 03 | **This Week**   | `due >= today()` + `due <= today() + "7d"`   | Week ahead              |
| 04 | **Upcoming**    | `due > today()` + `due <= today() + "7d"`    | Coming soon             |
| 05 | **Someday**     | `due == null` + `status != Done`             | No deadline yet         |

### Views/ — Type-Based Views

| # | Base Name        | Filters                    | Use Case              |
|---|------------------|----------------------------|----------------------|
| 01 | **Ideas**        | `type == ["Idea"]`         | Parking lot           |
| 02 | **Journal**      | `type == ["Journal"]`      | Daily notes/capture   |
| 03 | **Accounts**     | `type == ["Account"]`      | Account contexts      |
| 04 | **Goals**        | `type == ["Goal"]`         | OKR tracking          |
| 05 | **Projects**     | `type == ["Project"]`      | Portfolio overview    |
| 06 | **Epics**        | `type == ["Epic"]`         | Roadmap view          |
| 07 | **Stories**      | `type == ["Story"]`        | Sprint board          |
| 08 | **Bugs**         | `type == ["Bug"]`          | Bug triage            |
| 09 | **Contacts**     | `type == ["Contact"]`      | CRM / People          |
| 10 | **Meetings**     | `type == ["Meeting"]`      | Meeting log           |
| 11 | **Docs**         | `type == ["Documentation"]`| Documentation hub     |

---

## Workflows

### Capture → Process

1. **Quick capture:** Create item using appropriate template (type auto-filled)
2. **Daily triage:** Open Inbox Base, assign `parent`, `project`, `priority`, `area`, move to `Backlog` or `Active`

### Status Flow

```
Inbox → Backlog → Active → Done
                    ↓
                 Blocked/Waiting → Active → Done
```

- **Inbox:** Unprocessed, needs triage
- **Backlog:** Triaged but not yet started
- **Active:** Currently being worked
- **Blocked:** Waiting on external dependency
- **Waiting:** Delegated or scheduled for later
- **Done:** Completed
- **Archived:** Old/irrelevant, hidden from most views

### Daily Workflow

1. **Morning:** Review "Due Today", "Active Work", and "Meetings" in Daily Note
2. **During day:** Log progress, capture new items using templates
3. **End of day:** Update statuses, move completed to Done

### Meeting Workflow

1. **Before:** Create Meeting note, set `date`, link `project`, add `attendees`
2. **During:** Fill Agenda, take Notes
3. **After:** Log Decisions, create linked Tasks for Action Items, set status to `Done`

### Documentation Workflow

1. **Create:** Use Documentation template, set `doc_type`, link `project`
2. **Maintain:** Update `last_reviewed` when reviewed
3. **Monitor:** Use Dataview query to find stale documentation

---

## Naming Conventions

| Type          | Pattern                          | Example                              |
| ------------- | -------------------------------- | ------------------------------------ |
| Account       | Context/company name             | `Personal`, `Madali LLC`             |
| Goal          | Outcome statement                | `Launch MVP by Q2`                   |
| Project       | Descriptive name                 | `Platform Rebuild`                   |
| Epic          | Feature area                     | `Auth System`                        |
| Story         | User story format (optional)     | `User Login Flow`                    |
| Task          | Action verb + object             | `Implement JWT validation`           |
| Bug           | `[BUG]` prefix + description     | `[BUG] Session timeout not working`  |
| Idea          | Freeform                         | `AI-powered onboarding`              |
| Contact       | Full name                        | `John Doe`                           |
| Meeting       | Date + topic                     | `2025-01-15 Sprint Planning`         |
| Documentation | Topic + type                     | `Auth API Reference`                 |

---

## Template Summary

| Template      | Auto-Filled Type | Key Sections                                              |
|---------------|------------------|-----------------------------------------------------------|
| Account       | Account          | Overview, Vision, Key Metrics, Active Goals               |
| Goal          | Goal             | Objective, Key Results, Success Criteria, Review Cadence  |
| Project       | Project          | Scope (In/Out), Success Criteria, Key Dates, Stakeholders, Risks |
| Epic          | Epic             | Acceptance Criteria, Dependencies, Technical Considerations |
| Story         | Story            | User Story (As a/I want/So that), Acceptance Criteria     |
| Task          | Task             | Description, Checklist                                    |
| Bug           | Bug              | Summary, Steps to Reproduce, Expected/Actual              |
| Idea          | Idea             | Problem, Impact (Effort/Value), Next Steps                |
| Contact       | Contact          | Context, Interactions (frontmatter: email, phone, company, role) |
| Meeting       | Meeting          | Info, Attendees, Agenda, Notes, Decisions, Action Items   |
| Documentation | Documentation    | Overview, Audience, Content, Related, Changelog           |
| Journal       | Journal          | Focus, Notes, Ideas, Log                                  |

---

## Optional Enhancements

### Calculated Fields (Future)

If Obsidian Bases adds formulas:
- **Progress:** Count of Done children / Total children
- **Overdue:** `due < today AND status != Done`

### Dataview Fallback

For complex queries Bases can't handle yet:

```dataview
TABLE status, priority, due, project
FROM "Items"
WHERE parent = [[Auth Epic]] AND status != "Done"
SORT priority ASC
```

## Migration / Setup Checklist

- [ ] Create folder structure:
  - [ ] `Items/`
  - [ ] `Templates/`
  - [ ] `Bases/Status/`
  - [ ] `Bases/Timeline/`
  - [ ] `Bases/Views/`
  - [ ] `Resources/`
- [ ] Create all templates:
  - [ ] `Templates/Account Template.md`
  - [ ] `Templates/Goal Template.md`
  - [ ] `Templates/Project Template.md`
  - [ ] `Templates/Epic Template.md`
  - [ ] `Templates/Story Template.md`
  - [ ] `Templates/Task Template.md`
  - [ ] `Templates/Bug Template.md`
  - [ ] `Templates/Idea Template.md`
  - [ ] `Templates/Contact Template.md`
  - [ ] `Templates/Meeting Template.md`
  - [ ] `Templates/Documentation Template.md`
  - [ ] `Templates/Journal Template.md`
- [ ] Configure Templater or core Templates plugin
- [ ] Set Daily Notes plugin to use `Items/` folder and Journal Template
- [ ] Create initial Account item(s)
- [ ] Create 2-3 Goals linked to Account
- [ ] Create first Project linked to a Goal
- [ ] Build Bases views:
  - [ ] Status/: Inbox, Backlog, Active, Blocked, Done
  - [ ] Timeline/: Overdue, Today, This Week, Upcoming, Someday
  - [ ] Views/: Ideas, Journal, Accounts, Goals, Projects, Epics, Stories, Bugs, Contacts, Meetings, Docs
- [ ] Test capture → triage → complete workflow

---

## nvim Compatibility Notes

All data is portable:
- Notes are plain markdown
- Properties are standard YAML frontmatter (list syntax supported)
- Links use `[[wikilink]]` syntax (supported by obsidian.nvim)

Query examples for terminal/nvim:

```bash
# All active items
rg -l "status:" Items/ | xargs rg -l "Active"

# P1 bugs
rg -l "type:" Items/ | xargs rg -l "Bug" | xargs rg -l "P1"

# All items in a specific project
rg -l 'project:.*Platform Rebuild' Items/

# All meetings this month
rg -l "type:" Items/ | xargs rg -l "Meeting" | xargs rg -l "date:.*2025-01"

# Contacts at a specific company
rg -l "company:" Items/ | xargs rg -l "Acme"
```

---

*Last updated: 2025-11-26*

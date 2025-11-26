# my-obsidian

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Release](https://img.shields.io/github/v/release/mayknxyz/my-obsidian)](https://github.com/mayknxyz/my-obsidian/releases)
[![Obsidian](https://img.shields.io/badge/Obsidian-1.5+-purple)](https://obsidian.md)
[![GitHub Stars](https://img.shields.io/github/stars/mayknxyz/my-obsidian)](https://github.com/mayknxyz/my-obsidian/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/mayknxyz/my-obsidian)](https://github.com/mayknxyz/my-obsidian/commits)

A Bases-First Obsidian vault starter kit. Clone this repo and start organizing with dynamic views powered by [Obsidian Bases](https://obsidian.md/blog/bases/).

## What is this?

A flat-file, property-driven system where all items live in a single folder (`Items/`) with relationships managed via frontmatter links. No nested folder hierarchies—just properties and Bases views.

## Installation

1. Clone this repo into your Obsidian vaults folder
2. Open as a vault in Obsidian
3. Load the main workspace: `Ctrl+P` → "Workspaces: Load workspace" → `Main`
4. Configure core plugins (see Setup below)
5. Install Dataview plugin (for embedded queries)
6. Start creating items using the templates

> **Tip:** To pull future updates from this repo, avoid modifying default bases in `Status/`, `Timeline/`, and `Views/`. Instead, create custom bases in `Bases/Custom/` or duplicate existing ones.

## Setup

### Templates (Core Plugin)

1. Settings → Core plugins → Enable **Templates**
2. Settings → Templates:
   - Template folder: `Templates`
   - Date format: `YYYY-MM-DD` (or your preference)
   - Time format: `HH:mm`

### Daily Notes (Core Plugin)

1. Settings → Core plugins → Enable **Daily notes**
2. Settings → Daily notes:
   - New file location: `Items`
   - Template file: `Templates/Template: Journal`

### Files and Links (Core Plugin)

1. Settings → Files and links:
   - Default location for new attachments: `In the folder specified below`
   - Attachment folder path: `Files`

## Structure

```
Vault/
├── Bases/
│   ├── Custom/             # Your custom bases (won't conflict with updates)
│   ├── Status/             # Inbox, Backlog, Active, Blocked, Done
│   ├── Timeline/           # Overdue, Today, This Week, Upcoming, Someday
│   └── Views/              # Ideas, Journal, Goals, Projects, Wiki, etc.
├── Files/                  # Attachments - Core Plugin: Files and links
├── Items/                  # All typed items (flat) + Journal entries
├── Templates/              # Item templates - Core Plugin: Templates
└── REMINDERS.md            # Startup reminders (pinned tab)
```

## REMINDERS.md

A simple markdown file that opens as a pinned tab on startup (via the `Main` workspace). Use it for:

- **Daily habits** - Recurring checklist items
- **Important rules** - Things you should always remember
- **Don't forget** - Persistent reminders

Edit it directly anytime. No special syntax required—just plain markdown.

## Item Types

| Type | Purpose |
|------|---------|
| Template | Item templates |
| Account | Top-level context (personal, work, business) |
| Goal | OKRs and objectives |
| Project | Deliverable work |
| Epic | Feature grouping |
| Story | User-facing functionality |
| Task | Actionable work item |
| Feature | New capability or enhancement |
| Bug | Defect tracking |
| Idea | Parking lot for concepts |
| Journal | Quick capture, daily notes |
| Contact | People/CRM |
| Meeting | Meeting notes |
| Wiki | Code snippets, concepts, cheatsheets |

## Hierarchy

```
Account → Goal → Project → Epic → Story → Task/Feature/Bug
```

Supporting types (Contact, Meeting, Documentation) link via `project` or `parent`.

## Key Properties

- `type` - Item classification
- `status` - Inbox, Backlog, Active, Blocked, Waiting, Done, Archived
- `parent` - Direct parent link
- `project` - Root project (always set for nested items)
- `account` - Account context
- `area` - Dev, Ops, Marketing, Sales, Finance, Admin
- `priority` - P1, P2, P3
- `due` - Deadline
- `wiki` - Wiki category (Languages, Frameworks, Tools, Platforms)
- `link` - Technology reference as wiki link (e.g., `[[Python]]`, `[[Docker]]`)

## Status Flow

```
Inbox → Backlog → Active → Done
                    ↓
                 Blocked/Waiting
```

### Status Bases

```
Bases/Status/
├── 01 Blocked      # Unblock first
├── 02 Active       # Clear active actionable items
├── 03 Inbox        # Triage new actionable items
├── 04 Backlog      # Prep actionable items
├── 05 Unset        # Reassess + Set status
└── 06 Done         # Completed
```

## Recommended Plugins

- **Dataview** - For embedded queries in templates (required for template queries to work)

## Documentation

See [BLUEPRINT.md](BLUEPRINT.md) for the complete architecture, all templates, property schema, Bases configuration, and workflows.

## nvim Compatible

All data is plain markdown with YAML frontmatter. Works with [obsidian.nvim](https://github.com/epwalsh/obsidian.nvim).

## License

MIT

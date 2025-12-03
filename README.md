# my-obsidian

[![License: MIT](LICENSE.md)
[![Release](https://img.shields.io/github/v/release/mayknxyz/my-obsidian)](https://github.com/mayknxyz/my-obsidian/releases)
[![Obsidian](https://img.shields.io/badge/Obsidian-1.5+-purple)](https://obsidian.md)
[![GitHub Stars](https://img.shields.io/github/stars/mayknxyz/my-obsidian)](https://github.com/mayknxyz/my-obsidian/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/mayknxyz/my-obsidian)](https://github.com/mayknxyz/my-obsidian/commits)

A Bases-First Obsidian vault starter kit. Clone this repo and start organizing with dynamic views powered by [Obsidian Bases](https://obsidian.md/blog/bases/).

## What is this?

A flat-file, property-driven system where all items live in a single folder (`Items/`) with relationships managed via frontmatter links. No nested folder hierarchies—just properties and Bases views.

## Installation

1. **Fork** this repository (click "Fork" button on GitHub)
2. **Clone** your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/my-obsidian.git
   cd my-obsidian
   ```
3. **Add upstream remote** (for future updates):
   ```bash
   git remote add upstream https://github.com/mayknxyz/my-obsidian.git
   ```
4. **Open in Obsidian** as a vault
5. **Load workspace**: `Ctrl+P` → "Workspaces: Load workspace" → `Main`
6. **Configure** core plugins (see Setup below)

## Updating

Sync with the latest template updates:

```bash
git fetch upstream
git merge upstream/main
```

Your data in `Items/`, `Files/`, `Custom/`, and `REMINDERS.md` won't conflict since these folders start empty. Use `Custom/` for your own bases, templates, or any other files you want to keep separate from upstream updates.

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

### TaskNotes (Community Plugin)

1. Settings → Community plugins → Browse → Search "TaskNotes" → Install
2. Enable TaskNotes plugin
3. Settings → TaskNotes:
   - Base views folder: `Bases/Views`
   - Base views prefix: `08 Tasks`

TaskNotes manages all task creation, recurring tasks, and calendar integration. See [TaskNotes docs](https://tasknotes.dev/) for configuration.

## Structure

```
Vault/
├── Bases/
│   ├── Status/             # Inbox, Backlog, Active, Blocked, Done
│   ├── Timeline/           # Overdue, Today, This Week, Upcoming, Someday
│   └── Views/              # Ideas, Journal, Goals, Projects, Tasks (TaskNotes), etc.
├── Custom/                 # Your custom files (won't conflict with updates)
├── Docs/                   # System documentation (BLUEPRINT, CHANGELOG, etc.)
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
| Task | Actionable work item (managed by TaskNotes plugin) |
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
- `dept` - Dev, Ops, Marketing, Sales, Finance, Admin
- `context` - @home, @work, @computer, @phone, @errands (GTD contexts)
- `priority` - Low, Normal, High
- `due` - Deadline
- `scheduled` - Scheduled start date (TaskNotes)
- `estimate` - Time estimate (TaskNotes)
- `recurrence` - Recurrence pattern (TaskNotes)

See `Templates/Template: Property Defaults.md` for all property values.

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
- **TaskNotes** - Task management with calendar integration, recurring tasks, and time tracking ([docs](https://tasknotes.dev/))

## Documentation

See [BLUEPRINT.md](Blueprint.md) for the complete architecture, all templates, property schema, Bases configuration, and workflows.

## nvim Compatible

All data is plain markdown with YAML frontmatter. Works with [obsidian.nvim](https://github.com/epwalsh/obsidian.nvim).

## License

MIT

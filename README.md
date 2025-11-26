# my-obsidian

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
   - New file location: `Daily`
   - Template file: `Templates/Daily Template`

## Structure

```
Vault/
├── Bases/                  # Saved Base views
├── Daily/                  # Daily notes
├── Items/                  # All typed items (flat)
├── Resources/              # Reference material
├── Templates/              # Item templates
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
| Account | Top-level context (personal, work, business) |
| Goal | OKRs and objectives |
| Project | Deliverable work |
| Epic | Feature grouping |
| Story | User-facing functionality |
| Task | Actionable work item |
| Bug | Defect tracking |
| Idea | Parking lot for concepts |
| Contact | People/CRM |
| Meeting | Meeting notes |
| Documentation | Docs and references |

## Hierarchy

```
Account → Goal → Project → Epic → Story → Task/Bug
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

## Status Flow

```
Inbox → Backlog → Active → Done
                    ↓
                 Blocked/Waiting
```

## Recommended Plugins

- **Dataview** - For embedded queries in templates (required for template queries to work)

## Documentation

See [BLUEPRINT.md](BLUEPRINT.md) for the complete architecture, all templates, property schema, Bases configuration, and workflows.

## nvim Compatible

All data is plain markdown with YAML frontmatter. Works with [obsidian.nvim](https://github.com/epwalsh/obsidian.nvim).

## License

MIT

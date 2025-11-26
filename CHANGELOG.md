# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] - 2025-11-26

### Added

- REMINDERS.md - Persistent reminders file that opens as a pinned tab on startup
- Main workspace configuration (`.obsidian/workspaces.json`) with REMINDERS.md pinned
- Workspaces core plugin enabled for workspace management
- Documentation for REMINDERS.md in README.md and BLUEPRINT.md

## [0.1.0] - 2025-11-26

### Added

- Initial vault structure (Bases/, Daily/, Items/, Resources/, Templates/)
- 12 item templates:
  - Account Template (top-level context)
  - Goal Template (OKRs and objectives)
  - Project Template (deliverable work)
  - Epic Template (feature grouping)
  - Story Template (user-facing functionality)
  - Task Template (actionable work items)
  - Bug Template (defect tracking)
  - Idea Template (parking lot)
  - Contact Template (CRM with frontmatter properties)
  - Meeting Template (meeting notes)
  - Documentation Template (docs and references)
  - Daily Template (daily notes with dataview queries)
- BLUEPRINT.md with complete architecture documentation
- README.md with installation and setup instructions
- Property schema with 7 statuses (Inbox, Backlog, Active, Blocked, Waiting, Done, Archived)
- Type hierarchy: Account → Goal → Project → Epic → Story → Task/Bug
- 9 Bases view configurations (5 Core + 4 Strategic)
- Support for core Templates and Daily Notes plugins
- Dataview queries in templates for dynamic content
- nvim compatibility notes

[0.2.0]: https://github.com/mayknxyz/my-obsidian/releases/tag/v0.2.0
[0.1.0]: https://github.com/mayknxyz/my-obsidian/releases/tag/v0.1.0

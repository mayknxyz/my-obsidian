# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.8.0] - 2025-12-04

### Added

- TaskNotes plugin integration for task management
- 7 TaskNotes bases in `Bases/Views/` (08 Tasks*.base): table, agenda, calendar, kanban, mini-calendar, relationships, overview
- New properties for TaskNotes: `scheduled`, `estimate`, `recurrence`, `completed`, `modified`, `archived`, `blocked`, `pomodoros`, `reminders`, `complete_instances`, `icsEventId`, `ics_event`
- `context` property for GTD-style location/tool filtering (@home, @work, @computer, @phone, @errands)
- Custom hotkeys: `Alt+T` (insert template), `Ctrl+Shift+N` (create new task)

### Changed

- Renamed `area` property to `dept`
- Priority values changed from P1/P2/P3 to Low/Normal/High
- Task type now managed by TaskNotes plugin (removed Template: Task.md)

### Removed

- `Templates/Template: Task.md` (TaskNotes handles task creation)
- `Task` from type dropdown in Property Defaults

## [0.7.0] - 2025-11-27

### Added

- Property type definitions in `.obsidian/types.json` for all 21 properties (enables correct property behavior)
- `Templates/Template: Property Defaults.md` seed note with dropdown values for type, status, priority, area
- Wiki type filter to all Status bases (6 files) and Timeline bases (5 files)
- `priority` and `due` properties to Template: Wiki.md (makes Wiki an actionable item)

### Changed

- Wiki is now an actionable type (appears in Status and Timeline bases)
- Updated BLUEPRINT.md to include Wiki in actionable types list

### Removed

- Duplicate `wiki` and `link` property types from types.json (redundant with `parent`)

## [0.6.0] - 2025-11-26

### Changed

- Switch to fork-based installation for clean upstream updates
- Update README with fork/clone/upstream workflow
- Update CONTRIBUTING with PR guidelines for template-only changes

### Removed

- All sample items from Items/ (prevents merge conflicts on updates)

### Added

- .gitkeep files to preserve empty user folders (Items/, Files/, Custom/)
- Custom/ folder at root for user files (replaces Bases/Custom/)

## [0.5.0] - 2025-11-26

### Added

- Feature type with template and base view (09 Features.base)
- Wiki type with template and base view (13 Wiki.base)
- Feature type filter to all Status and Timeline bases
- Files/ folder for attachments (Core Plugin: Files and links)
- Bases/Custom/ folder for user-defined bases (won't conflict with repo updates)
- Files and Links setup instructions in README
- Tip in README about preserving default bases for pulling updates

### Changed

- Renamed all templates to "Template: {Name}.md" format
- Updated template frontmatter to use correct types (was `type: Template`, now actual type)
- Added `file.folder != "Templates"` filter to all 24 bases
- Removed Resources/ folder from documentation

## [0.4.0] - 2025-11-26

### Added

- Bases/Status/ with 6 status views: Blocked, Active, Inbox, Backlog, Unset, Done
- Bases/Timeline/ with 5 time-based views: Overdue, Today, This Week, Upcoming, Someday
- Bases/Views/ with 11 type-based views: Ideas, Journal, Accounts, Goals, Projects, Epics, Stories, Bugs, Contacts, Meetings, Docs
- Sample items demonstrating various item types (Account, Project, Story, Task, Bug, Contact, Meeting, Journal)
- Journal Template replacing Daily Template
- Status Bases documentation in README

### Changed

- Daily notes now use Journal Template
- Renamed "No Status" to "Unset" for clarity

### Removed

- .gitkeep placeholder files (Bases/, Daily/, Items/)
- Daily Template (replaced by Journal Template)
- Daily/ folder (journal entries now in Items/)

## [0.3.0] - Previous

- Add LICENSE, README badges, and contributing docs

## [0.2.0] - Previous

- Add REMINDERS.md startup reminders

## [0.1.0] - Previous

- Initial release

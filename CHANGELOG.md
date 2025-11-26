# Changelog

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

# Contributing to my-obsidian

Thanks for your interest in contributing! This project is a Bases-First Obsidian vault starter kit.

## How to Contribute

### Reporting Bugs

1. Check existing [issues](https://github.com/mayknxyz/my-obsidian/issues) to avoid duplicates
2. Use the bug report template
3. Include your Obsidian version and OS
4. Provide steps to reproduce the issue

### Suggesting Features

1. Check existing issues for similar suggestions
2. Use the feature request template
3. Explain the problem you're trying to solve
4. Describe your proposed solution

### Submitting Changes

1. Fork the repository
2. Add upstream remote: `git remote add upstream https://github.com/mayknxyz/my-obsidian.git`
3. Create a feature branch from latest upstream:
   ```bash
   git fetch upstream
   git checkout -b feature/your-feature upstream/main
   ```
4. Make changes to **template files only**:
   - `Templates/` - Item templates
   - `Bases/{Status,Timeline,Views}/` - Default bases
   - Documentation files (README, BLUEPRINT, etc.)
   - **Do not include** personal items from `Items/`, `Files/`, or `Bases/Custom/`
5. Test in a fresh Obsidian vault
6. Commit with a clear message
7. Push and open a Pull Request

## What We're Looking For

- New item templates
- Improved Bases configurations
- Documentation improvements
- Bug fixes

## Guidelines

- Keep the flat-file, property-driven philosophy
- Avoid adding plugin dependencies where possible
- Update BLUEPRINT.md if changing the architecture
- Test with Obsidian 1.5+

## Questions?

Open an issue with the question label.

# Documentation Structure

Use this structure consistently.

**See also:**
- [authority.md](authority.md) - Precedence rules when files conflict
- [file_creation_guide.md](file_creation_guide.md) - When to create each file type
- [README.md](../README.md) - Quick reference overview

## Root-level files

### Universal (all AI providers)
- **AGENTS.md** – Agent behavior and reasoning rules (highest priority)
- **AI_INSTRUCTIONS.md** – Session protocol and continuity rules (universal)
- **session_summary.md** – Last session snapshot for immediate resumption

### Provider-specific (thin wrappers)
- **CLAUDE.md** – Claude Code-specific additions
- **.cursorrules** – Cursor-specific additions
- **.github/copilot-instructions.md** – GitHub Copilot-specific additions

## docs/ directory
- **project_context.md** – What the project is (scope, architecture, status)
- **architecture_decisions.md** – Significant technical decisions and rationale
- **progress.md** – Current execution state (focus, completed, blocked, next)
- **authority.md** – Precedence rules when documentation conflicts
- **documentation_structure.md** – This file (meta-documentation)
- **file_creation_guide.md** – When to create each file type
- **future_notes.md** – Non-binding ideas and hypotheses
- **setup.md** – Environment setup and local development instructions
- **feature_specs/** – Detailed feature specifications and PRDs
  - **README.md** – Guidelines for creating and managing feature specs
  - **_TEMPLATE.md** – Template for new feature specifications
  - **prd.md** – Main project PRD (for single-product projects, create from _TEMPLATE.md)
  - **YYYY-MM-DD-feature-name.md** – Individual feature specs (for multi-feature projects)
# Claude Code Session Instructions

**Read these files in order:**

1. **AGENTS.md** – Behavior rules and reasoning style (universal)
2. **AI_INSTRUCTIONS.md** – Session protocol and continuity rules (universal)
3. This file – Claude Code-specific additions

---

## Claude Code-Specific Context

This file is automatically loaded by Claude Code when working in this repository.
It acts as persistent memory across all Claude Code sessions.

### What Claude Code provides

- Access to repository files and git operations
- Ability to run commands and tests
- Code editing and creation capabilities
- Web search when needed for current information

### Claude Code workflow integration

When working with Claude Code:
- Use `/init` command to bootstrap new projects
- Reference this template structure when setting up new repositories
- Follow the documentation-first workflow defined in AI_INSTRUCTIONS.md
- Update session_summary.md before ending each session

### Available commands

Consult Claude Code documentation for available slash commands and features.
Do not assume features exist without verification.

---

## Template-Specific Notes

This is a **template repository**.

When using this template for a real project:
1. Keep AGENTS.md and AI_INSTRUCTIONS.md as-is (or adapt minimally)
2. Replace `docs/project_context.md` with actual project description
3. Populate `docs/progress.md` with real work items
4. Create `docs/feature_specs/` for detailed requirements
5. Update `session_summary.md` after each work session

---

## Priority Reminder

If any content in this file conflicts with:
- **AGENTS.md** → AGENTS.md wins
- **AI_INSTRUCTIONS.md** → AI_INSTRUCTIONS.md wins

This file only adds Claude Code-specific context, it does not override universal rules.

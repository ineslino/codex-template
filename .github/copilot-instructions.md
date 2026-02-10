# GitHub Copilot Instructions

**Read these files in order:**

1. **AGENTS.md** – Behavior rules and reasoning style (universal)
2. **AI_INSTRUCTIONS.md** – Session protocol and continuity rules (universal)
3. This file – GitHub Copilot-specific additions

---

## GitHub Copilot-Specific Context

This file is automatically loaded by GitHub Copilot when working in this repository.

### What GitHub Copilot provides

- Code completion and suggestions
- Chat-based assistance
- Pull request summaries
- Code review assistance

### GitHub Copilot workflow integration

When working with GitHub Copilot:
- Use inline suggestions for code completion
- Use Copilot Chat for questions and explanations
- Follow the documentation-first workflow defined in AI_INSTRUCTIONS.md
- Update session_summary.md before ending each session

### Repository conventions

Before generating code:
- Read docs/project_context.md to understand the project
- Check docs/progress.md for current work state
- Review docs/architecture_decisions.md for technical constraints

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

This file only adds GitHub Copilot-specific context, it does not override universal rules.

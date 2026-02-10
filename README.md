# Codex Project Template

A documentation-first template for AI-assisted software development that guarantees continuity across sessions and AI providers.

## Purpose

This template ensures that projects can be resumed seamlessly by:
- Any AI provider (Claude, GPT, Gemini, etc.)
- Any human contributor
- After any amount of time

**Core principle:** The repository is the single source of truth. Never rely on chat memory.

---

## Quick Start

### For AI Agents Starting a Session

1. **Read AGENTS.md** – Behavior and reasoning rules
2. **Read AI_INSTRUCTIONS.md** – Session protocol and continuity rules
3. **Read your provider-specific file** (CLAUDE.md, .cursorrules, or .github/copilot-instructions.md)
4. Follow the session start protocol
5. Reconstruct context from documentation
6. Surface any gaps before proceeding

### For Humans Bootstrapping a New Project

1. Copy this template
2. Replace `docs/project_context.md` with your actual project description
3. Define initial scope in `docs/feature_specs/`
4. Start working, keeping documentation in sync

---

## File Structure

For detailed descriptions of each file, see [docs/documentation_structure.md](docs/documentation_structure.md).
For guidance on when to create files, see [docs/file_creation_guide.md](docs/file_creation_guide.md).

```
.
├── AGENTS.md                  # Agent behavior rules (HIGHEST PRIORITY)
├── AI_INSTRUCTIONS.md         # Session protocol (universal)
├── session_summary.md         # Last session snapshot
├── CLAUDE.md                  # Claude Code-specific additions
├── .cursorrules               # Cursor-specific additions
├── .github/
│   └── copilot-instructions.md # GitHub Copilot-specific additions
├── docs/
│   ├── project_context.md     # What the project is
│   ├── progress.md            # Current execution state
│   ├── architecture_decisions.md  # Technical decisions
│   ├── authority.md           # Precedence rules
│   ├── documentation_structure.md # This structure
│   ├── file_creation_guide.md # When to create files
│   ├── future_notes.md        # Non-binding ideas
│   ├── setup.md               # Environment setup
│   └── feature_specs/         # Detailed specifications (create when needed)
```

---

## Documentation Precedence

When documentation conflicts, follow this order (see [docs/authority.md](docs/authority.md) for complete rules):

1. **AGENTS.md** – behavior and reasoning rules (universal)
2. **AI_INSTRUCTIONS.md** – session protocol and continuity (universal)
3. **Provider-specific files** – CLAUDE.md, .cursorrules, .github/copilot-instructions.md (thin wrappers)
4. **Feature specs** – requirements and acceptance criteria
5. **project_context.md** – what exists and why
6. **architecture_decisions.md** – technical decision history
7. **progress.md + session_summary.md** – execution state
8. All other documentation

---

## Core Rules

### Documentation-First
- Read all relevant *.md files before acting
- Treat documentation as authoritative
- Update docs when changing code

### Traceability
- Every code change requires documentation update
- Record architectural decisions
- Track progress and session state

### No Silent Assumptions
- If documentation is unclear, stop and propose updates
- Make assumptions explicit
- Wait for confirmation before proceeding

### Provider-Agnostic
- No provider-specific features in outputs
- Works across Claude, GPT, Gemini, etc.
- Generic, well-documented implementation

---

## Session End Checklist

Before ending any session, update:

- [ ] `docs/progress.md` – current focus, completed, next actions
- [ ] `session_summary.md` – decisions, files changed, resume steps
- [ ] `docs/project_context.md` – if scope or architecture changed
- [ ] `docs/architecture_decisions.md` – if architectural choices were made

---

## Success Criteria

If this project were handed to a different AI provider or resumed after 6 months, it should be possible to continue seamlessly using only the repository and its Markdown files.

---

## Anti-Patterns

❌ Implementing features without updating `progress.md`
❌ Making architectural decisions without recording in `architecture_decisions.md`
❌ Assuming context from previous chat messages
❌ Leaving `session_summary.md` stale after work
❌ Proceeding with ambiguous requirements
❌ Using provider-specific features that break portability

---

## Template vs Project

This is a **template**. When starting a real project:

1. Keep AGENTS.md and AI_INSTRUCTIONS.md as-is (or adapt minimally)
2. Keep provider-specific files (CLAUDE.md, .cursorrules, .github/copilot-instructions.md) as-is
3. Replace `docs/project_context.md` with real project description
4. Populate `docs/progress.md` with actual work items
5. Create `docs/feature_specs/` for detailed requirements
6. Update `session_summary.md` after each session

The template provides structure, not content.

---

## License

This template is provided as-is for structuring AI-assisted software projects.

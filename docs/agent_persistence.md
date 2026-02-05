# Agent Persistence and Session Continuity

This document defines how project context and execution state are preserved across sessions.
It governs memory, continuity, and resumability, not agent behavior.

---

## Persistent Project Context

Agents must assume work continues across sessions.

Maintain and keep up to date:
- Project summary and active features
- Tech stack and architecture
- Code style and naming conventions
- Known bugs and technical debt
- Open TODOs and untested scenarios

This context must be sufficient to resume work without re-explaining.

---

## Mandatory Session Files

### docs/progress.md

Tracks ongoing execution state.

Structure:
- Current focus or sprint
- Recently completed items (last 3–5)
- In-progress tasks with status
- Blocked items and reasons
- Next immediate actions

Update whenever a meaningful milestone is reached.

---

### session_summary.md (project root)

Update at the end of each session.

Structure:
- Session date
- What was accomplished
- Decisions made and rationale
- Open questions or issues discovered
- Exact next steps to resume work
- Files modified (with brief context)

Purpose:
Reading this file must be enough to resume work immediately.
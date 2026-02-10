# Authority, Precedence, and Documentation Governance

This document defines how instructions, documentation, and decisions are prioritized and structured.
Its purpose is to eliminate ambiguity, prevent conflicts, and ensure consistent interpretation by humans and agents.

This file is authoritative for governance and precedence, but does not override AGENTS.md behavioral rules.

**See also:**
- [documentation_structure.md](documentation_structure.md) - What each file contains
- [file_creation_guide.md](file_creation_guide.md) - When to create each file type
- [README.md](../README.md) - Quick reference precedence summary

---

## 1. Instruction and Source Precedence

When instructions, documentation, or information conflict, follow this order strictly:

1. **AGENTS.md**
   - Defines agent behavior, output structure, reasoning style, and communication rules.
   - Supreme authority for how work is performed.
   - Universal across all AI providers.

2. **AI_INSTRUCTIONS.md**
   - Session protocol, continuity rules, and documentation-first workflow.
   - Defines how to start sessions, reconstruct context, and maintain traceability.
   - Universal across all AI providers.

3. **Provider-specific files** (CLAUDE.md, .cursorrules, .github/copilot-instructions.md)
   - Thin wrappers that reference AGENTS.md and AI_INSTRUCTIONS.md
   - Add only provider-specific context (features, commands, workflows)
   - Never override rules from AGENTS.md or AI_INSTRUCTIONS.md

4. **Feature specifications and PRDs**
   - Most recent approved versions take precedence.
   - Includes documents under `docs/feature_specs/`.

5. **`docs/project_context.md`**
   - Canonical description of the system, scope, architecture, and implemented behavior.
   - Represents the single source of truth for "what the system is."

6. **`docs/architecture_decisions.md`**
   - Records why significant architectural choices were made.
   - Historical and explanatory, not speculative.

7. **Execution state documents**
   - `docs/progress.md`
   - `session_summary.md`
   - Describe current and recent work state, blockers, and next actions.

8. **All other documentation**
   - Includes exploratory, historical, or supplementary material.
   - Never overrides higher-priority sources.

If two sources at the same level conflict, prefer:
- The most recent update
- The one closest to executable code or runtime behavior

---

## 2. Documentation Roles and Intent

Each document type has a distinct responsibility.
Documents must not duplicate responsibilities.

### Behavioral Rules
- **AGENTS.md**
  - How agents think, communicate, and decide
  - Assumption handling, confidence signaling, failure-first reasoning
  - Session continuity expectations

### System Truth
- **`docs/project_context.md`**
  - Project summary and goals
  - Implemented scope vs non-implemented scope
  - Tech stack and architecture overview
  - Non-negotiable project rules
  - Data model overview and common patterns

### Architectural History
- **`docs/architecture_decisions.md`**
  - Significant architectural decisions (ADRs)
  - Context, decision, rationale, consequences
  - Immutable once recorded, except for corrections

### Active Execution State
- **`docs/progress.md`**
  - Current focus or sprint
  - Recently completed work
  - In-progress tasks and blockers
  - Next immediate actions

- **`session_summary.md`**
  - Snapshot of the last working session
  - Decisions made and rationale
  - Exact steps required to resume work immediately

### Operational Onboarding
- **`docs/setup.md`**
  - Local development setup
  - Environment configuration
  - Runtime and testing instructions
  - No design intent or future planning

### Detailed Specifications
- **`docs/feature_specs/`**
  - PRDs and detailed feature documentation
  - Updated as scope or acceptance criteria evolve
  - Must align with implemented code or explicitly state gaps

### Exploratory or Non-Binding Content
- Optional documents such as future ideas or hypotheses
- Must be clearly labeled as non-authoritative
- Never assumed implemented unless reflected in code or higher-priority docs

---

## 3. Rules for Adding or Modifying Documentation

- Do not introduce new document types without clear justification.
- Do not duplicate content across files.
- Update the document that owns the responsibility, not a convenient one.
- If information becomes authoritative, move it to the correct higher-priority document.
- If information becomes obsolete, remove it rather than letting it drift.

---

## 4. Relationship to Code

When documentation conflicts with code:
- **Code wins**
- Documentation must be updated to reflect reality

Documentation describes intent and understanding.
Code defines actual behavior.

---

## 5. Goal of This Structure

This structure exists to ensure that:
- Agents can reason consistently across sessions
- Humans can resume work without re-explaining context
- Decisions are traceable
- Authority is unambiguous
- Drift is minimized over time

If something feels unclear, the structure is failing and should be corrected.
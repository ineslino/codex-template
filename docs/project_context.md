# Project Context – Codex Project Template

## 1. Purpose

This repository is a **project template** designed to standardize how projects are structured,
documented, and executed when using Codex as an active engineering assistant.

It provides:
- Clear separation between agent behavior and project-specific context
- Predictable repository and documentation structure
- Guardrails to prevent scope drift, over-engineering, and documentation noise
- Persistent continuity across Codex sessions

This template is intended to be **copied and adapted** for concrete projects.

---

## 2. What This Template Is (and Is Not)

This template:
- Defines *how work is organized*
- Defines *how Codex should behave*
- Defines *where information should live*
- Defines *how continuity is maintained*

This template does **not**:
- Define business requirements
- Define domain-specific logic
- Define technical architecture for a specific system
- Imply any implemented functionality

Concrete project details must be documented after bootstrapping.

---

## 3. Sources of Truth (Template Level)

When using this template, trust information in the following order:

1. **AGENTS.md** – agent behavior and reasoning rules
2. **docs/project_context.md** (this file) – template intent and usage
3. **docs/documentation_structure.md** – documentation placement rules
4. **docs/agent_persistence.md** – session continuity rules

Project-specific sources of truth must be defined in the derived project.

---

## 4. Repository Structure Philosophy

The template enforces:
- Simple, conventional repository layouts
- Minimal but explicit documentation
- Separation of concerns between:
  - Behavior rules
  - Project context
  - Active work
  - Historical decisions
  - Future ideas

Actual folder structures must follow **established best practices**
based on the project type (application, API, infrastructure, library, etc.).

If a project does not clearly match a known category, this must be decided explicitly.

---

## 5. Documentation Model

The template defines the following documentation roles:

- **AGENTS.md**  
  Agent behavior, reasoning rules, stop conditions

- **project_context.md**  
  Stable description of what the project *is*

- **feature_specs/**  
  PRDs, scoped feature descriptions, and delivery plans

- **progress.md**  
  Current execution state

- **session_summary.md**  
  Per-session continuity

- **architecture_decisions.md**  
  Irreversible or high-impact technical decisions

- **future_notes.md**  
  Ideas without commitment

Documentation must only be created when it adds material value.

---

## 6. Expected Usage Pattern

When bootstrapping a new project from this template:

1. Review and adjust `AGENTS.md` only if necessary
2. Replace this file (`project_context.md`) with project-specific context
3. Define initial scope in `feature_specs/`
4. Track execution in `progress.md`
5. Maintain continuity via `session_summary.md`

This file should be **rewritten or replaced** once the real project context exists.

---

## 7. Non-Goals

This template explicitly avoids:
- Enforcing rigid process frameworks
- Auto-generating documentation
- Encoding language- or framework-specific structures
- Acting as a substitute for engineering judgment

The goal is discipline, not rigidity.

---

## 8. Template Scope Boundaries

Anything not explicitly defined by this template:
- Must be decided per project
- Must be documented in project-level context
- Must not be inferred by Codex

The template provides guardrails, not answers.
# File Creation Guide

This document explains when and how to create each type of file in this template.

---

## Files That Exist From Template Start

These files are part of the template and should **not be deleted**:

### Universal Rules (Do Not Modify)
- **AGENTS.md** - Behavior and reasoning rules
- **AI_INSTRUCTIONS.md** - Session protocol and continuity
- **README.md** - Template overview and quick start

### Provider-Specific Wrappers (Keep As-Is)
- **CLAUDE.md** - Claude Code instructions
- **.cursorrules** - Cursor instructions
- **.github/copilot-instructions.md** - GitHub Copilot instructions

### Documentation Framework
- **docs/authority.md** - Precedence rules
- **docs/documentation_structure.md** - File structure reference
- **docs/file_creation_guide.md** - This file
- **docs/architecture_decisions.md** - ADR template (populate when decisions are made)
- **docs/future_notes.md** - Non-binding ideas placeholder

### Execution State (Update Every Session)
- **session_summary.md** - Last session snapshot
- **docs/progress.md** - Current execution state

### Template Placeholders (Replace When Bootstrapping)
- **docs/project_context.md** - Replace with actual project description
- **docs/setup.md** - Replace with actual setup instructions

### Feature Specifications
- **docs/feature_specs/README.md** - Guidelines for feature specs
- **docs/feature_specs/_TEMPLATE.md** - PRD template (copy and rename when needed)

---

## Files to Create During Project Bootstrap

When starting a **new project** from this template:

### 1. Replace Template Placeholders

**docs/project_context.md** - Replace immediately
```markdown
# Project Context

## 1. Purpose
What does this project do? Why does it exist?

## 2. Scope
What's in scope? What's explicitly out of scope?

## 3. Architecture
High-level technical architecture and key decisions

## 4. Tech Stack
Languages, frameworks, tools, services

## 5. Current Status
What's implemented? What's in progress?
```

**docs/setup.md** - Replace with real setup instructions
- Prerequisites and dependencies
- Installation steps
- Local development commands
- Troubleshooting

### 2. Create Initial PRD/Feature Specs

**For single-product or MVP projects (recommended):**
```bash
# Create main PRD
cp docs/feature_specs/_TEMPLATE.md docs/feature_specs/prd.md

# Fill in:
# - Overall product goals and non-goals
# - User stories for MVP
# - Requirements
# - Implementation plan
```

**For multi-feature projects:**
```bash
# Create dated feature specs
cp docs/feature_specs/_TEMPLATE.md docs/feature_specs/2026-02-10-feature-name.md

# Fill in details for this specific feature
```

**Decision guide:**
- Use `prd.md` for unified products, MVPs, or single-feature projects
- Use dated specs when managing independent features or a feature roadmap

### 3. Initialize Execution State

**docs/progress.md** - Set initial state
```markdown
## Current focus
- Project bootstrap and initial setup

## Recently completed
- Created repository from template
- Updated project_context.md with actual project details

## Next actions
- Define initial feature scope
- Set up development environment
- Create first feature spec
```

**session_summary.md** - Document bootstrap session
- Date and accomplishments
- Initial decisions made
- Next steps to resume work

---

## Files to Create During Development

### When Making Architectural Decisions

**Add entry to docs/architecture_decisions.md**

Trigger: Any decision that affects:
- System architecture or structure
- Technology choices (frameworks, databases, services)
- Non-reversible or high-cost decisions
- Patterns or conventions that will be followed

Format:
```markdown
## ADR-001 - [Decision Name]

**Date:** YYYY-MM-DD
**Status:** Proposed | Accepted | Deprecated | Superseded by ADR-XXX

### Context
What's the situation? What forces are at play?

### Decision
What are we doing?

### Rationale
Why this approach over alternatives?

### Consequences
What are the implications? Trade-offs? Limitations?
```

### When Starting a New Feature

**Option 1: Update existing prd.md (single-product projects)**

If you already have `docs/feature_specs/prd.md`, **add the new feature to the existing document:**

Steps:
1. Add feature to "Features" section with status "Planned"
2. Add specific requirements to "Functional Requirements"
3. Update "Implementation Plan" with new phases/tasks
4. Update "Timeline and Milestones" with dates
5. Add entry to "Change Log" documenting the addition

**The goal:** One `prd.md` that evolves with your product, containing all features (past, present, and planned).

**Option 2: Create new feature spec (multi-feature projects)**

**Create: docs/feature_specs/YYYY-MM-DD-feature-name.md**

Trigger: When implementing any feature that:
- Is independent from the main product (optional module, plugin, etc.)
- Requires multiple files or sessions
- Needs clarification or alignment
- Has non-obvious requirements
- Should be documented separately for continuity

Steps:
1. Copy `docs/feature_specs/_TEMPLATE.md`
2. Rename with date prefix: `YYYY-MM-DD-feature-name.md`
3. Fill in all relevant sections
4. Get approval before implementation (set Status: Approved)

**Decision guide:**
- Use `prd.md` for core product features
- Use dated specs for optional features, plugins, or independent modules

### When Discovering Non-Binding Ideas

**Add to docs/future_notes.md**

Trigger: Ideas that are:
- Not committed to implementation
- Exploratory or speculative
- "Nice to have" without clear priority
- Deferred for later consideration

**Do NOT add to future_notes.md:**
- Committed work (use progress.md)
- Approved requirements (use feature_specs/)
- Architectural decisions (use architecture_decisions.md)

### Adding New Provider Support

**Create provider-specific wrapper file**

Examples:
- `.junie/guidelines.md` (JetBrains)
- `WINDSURF.md` (Windsurf)
- `AIDER.md` (Aider)

Format (always references universal files):
```markdown
# [Provider Name] Instructions

**Read these files in order:**

1. **AGENTS.md** – Behavior rules (universal)
2. **AI_INSTRUCTIONS.md** – Session protocol (universal)
3. This file – [Provider]-specific additions

## [Provider]-Specific Context
[Only add provider-specific features/commands here]

## Priority Reminder
If any content conflicts with AGENTS.md or AI_INSTRUCTIONS.md,
those files take precedence.
```

---

## Files You Should NOT Create

### ❌ Do Not Create Duplicates

- **README files in subdirectories** - One README.md at root is sufficient
- **Additional .gitignore files** - Use root .gitignore
- **Multiple architecture docs** - Use architecture_decisions.md with numbered ADRs
- **Separate "goals" or "vision" docs** - Put in project_context.md

### ❌ Do Not Create Documentation By Default

Avoid creating:
- CONTRIBUTING.md (unless project has external contributors)
- CODE_OF_CONDUCT.md (unless required)
- CHANGELOG.md (until project has releases)
- LICENSE (until distribution model is clear)
- Separate testing docs (put in setup.md or feature specs)

**Principle:** Create documentation when it adds material value, not by default.

---

## Decision Tree: Which File Should I Update?

```
New information to document?
│
├─ Is it about agent behavior/reasoning?
│  └─ Update: AGENTS.md
│
├─ Is it about session protocol/workflow?
│  └─ Update: AI_INSTRUCTIONS.md
│
├─ Is it a provider-specific feature?
│  └─ Update: CLAUDE.md, .cursorrules, or .github/copilot-instructions.md
│
├─ Is it an architectural decision?
│  └─ Add ADR to: docs/architecture_decisions.md
│
├─ Is it a feature requirement?
│  └─ Create/update: docs/feature_specs/YYYY-MM-DD-feature-name.md
│
├─ Does it describe what the project IS?
│  └─ Update: docs/project_context.md
│
├─ Is it about current work state?
│  ├─ Current session → Update: session_summary.md
│  └─ Overall progress → Update: docs/progress.md
│
├─ Is it setup/environment related?
│  └─ Update: docs/setup.md
│
├─ Is it a non-committed idea?
│  └─ Add to: docs/future_notes.md
│
└─ Does it explain the documentation system itself?
   ├─ Precedence rules → Update: docs/authority.md
   ├─ File structure → Update: docs/documentation_structure.md
   └─ When to create files → Update: docs/file_creation_guide.md (this file)
```

---

## Summary

**Template Start:**
- All universal and framework files exist
- Template placeholders are marked for replacement

**Project Bootstrap:**
- Replace project_context.md
- Replace setup.md
- Initialize progress.md and session_summary.md
- Optionally create initial feature specs

**During Development:**
- Add ADRs when making architectural decisions
- Create feature specs for non-trivial features
- Update progress.md and session_summary.md every session
- Add ideas to future_notes.md (not committed work)

**Never Create:**
- Duplicate documentation
- Provider-specific content in universal files
- Documentation without clear value

**When in Doubt:**
Check the decision tree above or ask before creating new files.

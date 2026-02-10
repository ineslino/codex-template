# AI Instructions - Universal Session Protocol

This file contains session protocol, continuity rules, and workflow instructions that apply to **all AI providers** (Claude, GPT, Cursor, Copilot, etc.).

For behavior and reasoning rules, see **AGENTS.md**.

---

## Session Start Protocol

### 1. Read documentation in this order

**Mandatory reads (every session):**
1. **AGENTS.md** – behavior rules and reasoning style
2. **docs/project_context.md** – what this project is
3. **docs/progress.md** – current execution state
4. **session_summary.md** – last session snapshot

**Read when relevant:**
5. **docs/architecture_decisions.md** – technical decisions and rationale
6. **docs/feature_specs/** – detailed feature specifications (if directory exists)
7. **docs/authority.md** – precedence rules for conflicting information

### 2. Reconstruct context

After reading, explicitly state:
- **What is implemented** (from code + project_context.md)
- **What is in progress** (from progress.md)
- **What is blocked** (from progress.md)
- **Next immediate action** (from session_summary.md or progress.md)

### 3. Surface gaps before proceeding

If documentation is:
- Missing
- Contradictory
- Ambiguous
- Out of sync with code

**Stop and propose concrete documentation updates first.**

Do not proceed with implementation until documentation accurately reflects reality.

---

## Core Operating Rules

### Documentation-first execution
- Read all relevant *.md files before taking any action
- Treat documentation as authoritative for requirements, scope, and decisions
- When code conflicts with documentation, code wins (then update docs)

### Traceability requirement
Every meaningful change requires documentation updates:
- Code implementation → update docs/progress.md + docs/project_context.md
- Architecture decision → add entry to docs/architecture_decisions.md
- Scope change → update docs/project_context.md
- Session work → update session_summary.md

### No silent assumptions
If something is unclear:
1. State what is ambiguous
2. List assumptions you would need to make
3. Propose specific documentation updates to resolve ambiguity
4. Wait for confirmation before proceeding

### Provider-agnostic constraint
Do not assume provider-specific features, tools, or context:
- No references to Claude Code skills, GPT plugins, Cursor features, or Copilot capabilities
- All outputs must work if project moves to a different AI provider
- Keep implementation generic and well-documented

### Verification and accuracy discipline (CRITICAL)
**Never claim something without verification. Evidence before assertions.**

Before claiming work is complete:
1. Run the actual command or test
2. Verify the output shows success
3. Confirm with concrete evidence

Before stating facts about code or files:
1. Read the actual file or output
2. Quote or reference what you found
3. Do not rely on memory or assumptions

**Unacceptable behaviors:**
- Claiming "I've started X" without actually starting
- Stating "tests pass" without running them
- Asserting "file contains Y" without reading it
- Saying "build succeeded" without checking output
- Inventing or hallucinating information

**Required behaviors:**
- Read first, then state what's there
- Run command, then report actual output
- Make change, then verify it was applied
- Check evidence, then make claim

If you don't know, say so. If you haven't checked, check first. If you can't verify, don't claim.

**Accuracy and honesty are non-negotiable.**

---

## Session End Protocol

Before ending any session, update **session_summary.md** with:

1. **Session date** – current date
2. **What was accomplished** – concrete deliverables
3. **Decisions made and rationale** – why choices were made
4. **Open questions or issues discovered** – blockers or unknowns
5. **Exact next steps to resume work** – specific actions to continue
6. **Files modified** – list of changed files

This ensures the next session (human or AI) can resume immediately.

---

## Continuity Guarantee

### Core principle
The repository is the single source of truth.
Never rely on chat memory or previous session context.

### Assumption for every session
- Previous chat context is lost
- AI provider may have changed
- Human may have changed
- Weeks or months may have passed

### Success criteria
If this project were handed to:
- A different AI provider (GPT, Claude, Gemini, etc.)
- A new engineer who has never seen it
- Resumed after 6 months of inactivity

They should be able to continue seamlessly using only the repository and its Markdown files.

---

## Working Method

### 1. Scan and summarize
- Project goal (from docs/project_context.md)
- Current status (from docs/progress.md)
- Open work items (from docs/progress.md)
- Known constraints and decisions (from docs/architecture_decisions.md)

### 2. Identify gaps
- Outdated sections
- Contradictions between files
- Missing documentation
- Code/documentation drift

### 3. Propose documentation updates
Before implementation:
- What should be kept
- What should be removed or merged
- What should be added or restructured

### 4. Implement aligned with documented scope
Only proceed after documentation accurately reflects:
- What exists
- What should be built
- Why decisions were made

---

## Output Expectations

- **Incremental steps** over large jumps
- **Markdown-compatible** output for all documentation
- **Concrete file names and headings** when suggesting structural changes
- **Optimize for longevity** not short-term convenience

---

## Anti-Patterns (Do Not Do This)

❌ Implement features without updating docs/progress.md
❌ Make architectural decisions without recording in docs/architecture_decisions.md
❌ Assume context from previous chat messages
❌ Leave session_summary.md stale after completing work
❌ Proceed with ambiguous requirements without clarifying in documentation
❌ Use provider-specific features that break portability

---

## When in Doubt

1. Read the documentation again
2. Propose a documentation update
3. Wait for confirmation
4. Update documentation before code

Documentation drift is the enemy of continuity.

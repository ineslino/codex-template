# Feature Specifications Directory

This directory contains Product Requirement Documents (PRDs) and detailed feature specifications.

## Purpose

Each feature spec should answer:
- **What** are we building?
- **Why** are we building it?
- **Who** is it for?
- **How** will we know it's successful?

## When to Create a Feature Spec

Create a feature spec when:
- Implementing a non-trivial feature
- Work requires multiple sessions or files
- Requirements need clarification or alignment
- Decision rationale should be preserved

**Do not create specs for:**
- Bug fixes (use issue tracker or commit messages)
- Simple one-line changes
- Experimental or exploratory work

## File Naming Convention

### For single-product/MVP projects (recommended starting point)
Use **`prd.md`** as your main Product Requirements Document:
```bash
cp _TEMPLATE.md prd.md
```

This is the **primary PRD** for the overall project. Update it as requirements evolve.

### For multi-feature projects
Create separate feature specs with date prefixes:
```
YYYY-MM-DD-feature-name.md
```

Examples:
- `2026-02-10-user-authentication.md`
- `2026-03-15-api-rate-limiting.md`
- `2026-04-20-dashboard-redesign.md`

Date prefix ensures chronological ordering and provides context for when requirements were defined.

### Decision guide
- **Use prd.md when:** Building a single product, MVP, or unified system
- **Use dated specs when:** Managing multiple independent features or a roadmap with discrete deliverables

## Template Structure

Copy `_TEMPLATE.md` and rename it based on your needs (see naming convention above).

---

## Working with prd.md (Multi-Feature Projects)

If using `prd.md` as your main PRD, treat it as a **living document** that grows with your product.

### When adding a new feature to prd.md:

1. **Add to "Features" section**
   - Add new feature with status "Planned"
   - Include priority (P0/P1/P2)
   - Brief description and key requirements

2. **Update "Functional Requirements"**
   - Add specific requirements for the new feature
   - Mark priority level (Must Have / Should Have / Nice to Have)

3. **Update "Implementation Plan"**
   - Add new phases or tasks for the feature
   - Update deliverables and testing strategy

4. **Update "Timeline and Milestones"**
   - Add milestone dates for the new feature

5. **Add to "Change Log"**
   - Document when the feature was added and by whom

### As features progress:
- Update feature status: Planned → In Progress → Completed
- Keep requirements and implementation details current
- Mark acceptance criteria as completed

**The goal:** `prd.md` reflects the **current and planned state** of your entire product in one document.

---

## Relationship to Other Documentation

**Feature specs define WHAT to build.**

Once implemented, update:
- **docs/project_context.md** – Add feature to "What is implemented"
- **docs/progress.md** – Mark as completed
- **docs/architecture_decisions.md** – Record any architectural decisions made during implementation
- **session_summary.md** – Document implementation decisions and trade-offs

Feature specs are living documents during active development, then become historical records after implementation.

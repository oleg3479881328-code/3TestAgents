# Workflow Artifact Standard

## Purpose

This document defines the canonical workflow artifact structure for all future workflow runs.

Goal:
Create deterministic, reviewable, reusable workflow packets independent from the executing agent.

Applies to:
- ChatGPT;
- Codex;
- future agents;
- workflow orchestration;
- repository governance.

---

## 1. Core Principle

Every workflow run must produce a predictable artifact structure.

Reason:
Without deterministic workflow packets:
- review quality drifts;
- logs diverge;
- handoffs become inconsistent;
- repository memory fragments;
- workflow reuse becomes unreliable.

---

## 2. Canonical Workflow Packet

Default workflow run structure:

```text
workflow-runs/<run-id>/
  00_INPUT.md
  01_BRIEF.md
  02_RESEARCH_REPORT.md
  03_ARCHITECTURE_SPEC.md
  04_CODER_SPEC.md
  05_REVIEW_REPORT.md
  06_LIBRARY_EXTRACT.md
  07_HANDOFF_NOTE.md
```

Compact single-file workflow records are allowed only for small tasks if they preserve the same logical sections.

---

## 3. Artifact Definitions

### 00_INPUT.md

Purpose:
Capture the raw user request, problem statement, constraints, and initial context.

### 01_BRIEF.md

Purpose:
Transform raw input into structured problem definition.

### 02_RESEARCH_REPORT.md

Purpose:
Capture reusable patterns, references, open-source examples, and prior art.

### 03_ARCHITECTURE_SPEC.md

Purpose:
Define architecture, repository structure, boundaries, lifecycle rules, and system contracts.

### 04_CODER_SPEC.md

Purpose:
Produce implementation-ready tasks and artifact requirements.

### 05_REVIEW_REPORT.md

Purpose:
Identify contradictions, risks, governance violations, scope drift, and unresolved decisions.

### 06_LIBRARY_EXTRACT.md

Purpose:
Extract reusable patterns, lessons, anti-patterns, and operational knowledge.

### 07_HANDOFF_NOTE.md

Purpose:
Provide deterministic continuation context for another agent or future session.

---

## 4. Required Sections Per Artifact

Every artifact should contain when applicable:

- purpose;
- scope;
- inputs;
- outputs;
- evidence;
- decisions;
- risks;
- unresolved questions;
- next step;
- state label.

---

## 5. State Labels

Artifacts must distinguish:

### Generated

AI-proposed but not committed.

### Committed

Written to repository.

### Reviewed

Passed explicit review.

### Active

Approved for operational reuse.

### Derived

Generated from repository state or analysis tools.

---

## 6. Handoff Rules

`07_HANDOFF_NOTE.md` must align with:

- `templates/HANDOFF_NOTE_TEMPLATE.md`
- `docs/REPO_MEMORY_STANDARD.md`
- `docs/WORKFLOW_ENFORCEMENT_RULES.md`

The handoff note must never replace:
- migration snapshot;
- workflow log;
- registry state.

---

## 7. Workflow Acceptance Criteria

A workflow run is considered structurally complete only if:

- required artifacts exist;
- review artifact exists;
- handoff artifact exists;
- workflow log updated when needed;
- migration snapshot updated when needed;
- registry/indexes updated when needed.

---

## 8. Current Repository Policy

Current project phase:
Document-first AI Skill Infrastructure.

Current enforcement priority:
Deterministic workflow structure before runtime expansion.

Forbidden priorities:
- backend;
- runtime engines;
- orchestration systems;
- automation layers;
- vector databases;
- semantic search;
- uncontrolled mass workflow generation.

---

## 9. Standard Decision

`WORKFLOW_ARTIFACT_STANDARD.md` is now a core governance document.

All future workflow runs should comply with this standard unless the user explicitly approves an exception.

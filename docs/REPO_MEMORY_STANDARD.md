# Repo Memory Standard — ChatGPT + Codex

## Purpose

This standard defines how ChatGPT, Codex, and future agents must use repository memory, navigation artifacts, workflow logs, skill registries, and derived graph artifacts inside this repository.

Goal:
Create one shared operating standard so agents do not duplicate work, lose context, invent state, or navigate the repository blindly.

---

## 1. Core Principle

The repository is the source of truth.

Chat messages, generated plans, and agent reasoning are not executed state unless they are backed by repository artifacts, commits, explicit tool output, or user-confirmed execution.

---

## 2. Required Read Order for Fresh Context

Any agent entering the project must read in this order:

1. `docs/MIGRATION_SNAPSHOT.md`
2. `logs/WORKFLOW_LOG.md`
3. `skills/PROJECT_INDEX.md`
4. `skills/registry.md`
5. `knowledge-library/PROJECT_INDEX.md`
6. `docs/PROJECT_RULES.md`
7. `workflow-runs/002-ai-skill-system-run.md`

If Graphify artifacts exist, read them after the migration snapshot and before raw file exploration:

8. `graphify-out/GRAPH_REPORT.md`
9. `graphify-out/graph.json` when machine navigation is needed

---

## 3. Role of Each Memory Layer

### MIGRATION_SNAPSHOT.md

Main entry point for a fresh chat, new agent, or continuation session.

Purpose:
- current project state;
- confirmed decisions;
- restrictions;
- active phase;
- next step.

### WORKFLOW_LOG.md

Executed history log.

Purpose:
- what was actually done;
- what changed;
- why it changed;
- resulting state;
- risks and lessons.

### skills/registry.md

Canonical skill registry.

Purpose:
- list known skills;
- lifecycle status;
- review status;
- compatibility;
- version;
- path.

### skills/PROJECT_INDEX.md

Human navigation index for the skill layer.

Purpose:
- categories;
- current skill count;
- priorities;
- forbidden expansion zones.

### knowledge-library/PROJECT_INDEX.md

Human navigation index for reusable knowledge.

Purpose:
- patterns;
- decisions;
- anti-pattern candidates;
- workflow lessons.

### graphify-out/GRAPH_REPORT.md

Repository cognition report.

Purpose:
- compressed codebase/repository map;
- navigation aid;
- structural overview;
- first-read artifact for codebase questions when present.

### graphify-out/graph.json

Machine-readable repository graph.

Purpose:
- future machine traversal;
- dependency navigation;
- structural querying;
- agent-assisted repository exploration.

---

## 4. ChatGPT Responsibilities

ChatGPT should:
- maintain strategy, architecture, governance, and documentation consistency;
- create or update Markdown source-of-truth files when appropriate;
- avoid claiming execution without repository evidence;
- preserve MVP boundaries;
- identify missing standards, logs, and governance gaps;
- propose controlled next steps only.

ChatGPT must not:
- invent repository state;
- claim Codex executed something unless evidence exists;
- push runtime, backend, automation, or large expansion before governance approval;
- create mass skills without registry and review.

---

## 5. Codex Responsibilities

Codex should:
- perform local repository edits when assigned;
- read repository memory before changing files;
- check `docs/MIGRATION_SNAPSHOT.md` before planning;
- check `graphify-out/GRAPH_REPORT.md` when available before codebase navigation;
- update affected docs, indexes, logs, and registries after changes;
- preserve repository structure and existing decisions.

Codex must not:
- bypass repository standards;
- create implementation without checking MVP restrictions;
- treat generated plans as executed state;
- ignore registry or workflow log updates;
- create runtime or automation unless explicitly approved by current project phase.

---

## 6. Graphify Standard

Graphify is a repository cognition layer, not a runtime dependency.

If introduced into this repository later, Graphify artifacts should live in:

```text
graphify-out/
  GRAPH_REPORT.md
  graph.json
  graph.html
```

Rules:
- `GRAPH_REPORT.md` is the human-first navigation artifact.
- `graph.json` is the machine-first navigation artifact.
- Graphify output is derived state, not source-of-truth architecture.
- Agents should read `GRAPH_REPORT.md` before raw repository exploration when it exists.
- Graphify must not become a runtime dependency without explicit approval.

---

## 7. Update Rules After Any Significant Change

After a meaningful repository change, update the relevant memory files.

### Always consider updating:

- `logs/WORKFLOW_LOG.md`
- `docs/MIGRATION_SNAPSHOT.md`

### If skills changed:

- `skills/registry.md`
- `skills/PROJECT_INDEX.md`
- relevant skill `SKILL.md`
- relevant `validation/REVIEW.md`

### If reusable patterns changed:

- `knowledge-library/PROJECT_INDEX.md`
- relevant knowledge-library entry

### If codebase structure changed and Graphify exists:

- regenerate Graphify artifacts;
- update `graphify-out/GRAPH_REPORT.md`;
- update `graphify-out/graph.json`.

---

## 8. State Labels

Agents must distinguish these states:

### Generated State

Proposed by AI but not committed or executed.

### Committed State

Written to repository.

### Reviewed State

Checked by reviewer or review process.

### Active State

Approved for operational reuse.

### Derived State

Generated from repository content, such as Graphify artifacts.

Derived state supports navigation but does not override source-of-truth documents.

---

## 9. Conflict Resolution

If files disagree, use this priority order:

1. Explicit user instruction in current task
2. `docs/MIGRATION_SNAPSHOT.md`
3. `docs/PROJECT_RULES.md`
4. `logs/WORKFLOW_LOG.md`
5. `skills/registry.md`
6. `skills/PROJECT_INDEX.md`
7. `knowledge-library/PROJECT_INDEX.md`
8. `graphify-out/GRAPH_REPORT.md`
9. individual workflow runs
10. raw chat history

If conflict remains, stop and create a documented decision before editing.

---

## 10. Current Project Phase

Current phase:
Document-first AI Skill Infrastructure.

Current subphase:
Governance stabilization and first skill validation.

Allowed:
- documentation refinement;
- review cycles;
- registry maintenance;
- knowledge-library improvement;
- repo-memory standardization.

Forbidden unless explicitly approved:
- backend;
- frontend;
- runtime engine;
- orchestration engine;
- automation layer;
- vector database;
- semantic search;
- marketplace;
- mass skill creation.

---

## 11. Standard Decision

This file is the shared operating standard for ChatGPT, Codex, and future agents working in this repository.

Agents must use it to align repository memory, navigation, documentation updates, and execution claims.

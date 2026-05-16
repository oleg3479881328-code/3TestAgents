# Workflow Enforcement Rules

## Purpose

This document converts repository standards into mandatory workflow behavior.

Goal:
Ensure all future workflow runs, ChatGPT sessions, Codex sessions, and future agents follow the same repository-memory and governance rules.

---

## 1. Mandatory Repository Memory Standard

All future workflow runs must follow:

`docs/REPO_MEMORY_STANDARD.md`

This is not optional guidance.

It is the required operating standard for:
- ChatGPT;
- Codex;
- future agents;
- workflow orchestration;
- repository-memory handling.

---

## 2. Mandatory Read Order Before Work

Before planning, architecture, review, implementation, or repository edits, agents must read:

1. `docs/MIGRATION_SNAPSHOT.md`
2. `logs/WORKFLOW_LOG.md`
3. `skills/PROJECT_INDEX.md`
4. `skills/registry.md`
5. `knowledge-library/PROJECT_INDEX.md`
6. `docs/PROJECT_RULES.md`
7. `docs/REPO_MEMORY_STANDARD.md`

If Graphify exists:

8. `graphify-out/GRAPH_REPORT.md`

---

## 3. Workflow Enforcement

Every workflow run must:
- preserve generated vs committed vs reviewed vs active state separation;
- update logs after meaningful repository changes;
- update registry after skill changes;
- update migration snapshot after major state changes;
- preserve document-first boundaries;
- avoid fake execution claims.

---

## 4. Forbidden Workflow Behavior

Forbidden:
- mass skill creation without review;
- runtime expansion before approval;
- backend creation outside approved phase;
- automation layer creation outside approved phase;
- repository edits without reading migration snapshot;
- architectural drift without documented decision.

---

## 5. Required Artifact Maintenance

After meaningful changes:

Always evaluate updates for:
- `docs/MIGRATION_SNAPSHOT.md`
- `logs/WORKFLOW_LOG.md`

If skills changed:
- `skills/registry.md`
- `skills/PROJECT_INDEX.md`

If reusable knowledge changed:
- `knowledge-library/PROJECT_INDEX.md`

If Graphify exists and structure changed:
- regenerate Graphify artifacts.

---

## 6. Current Enforcement Phase

Current repository phase:
Document-first AI Skill Infrastructure.

Current enforcement priority:
Governance stability over growth speed.

Meaning:
- quality before quantity;
- review before activation;
- governance before runtime;
- repository memory before automation.

---

## 7. Enforcement Decision

All future workflow runs inside this repository must comply with:
- `docs/PROJECT_RULES.md`
- `docs/REPO_MEMORY_STANDARD.md`
- `docs/WORKFLOW_ENFORCEMENT_RULES.md`

These documents form the repository governance foundation.

# Workflow Validation Checklist

## Purpose

Lightweight validation before accepting workflow runs or governance changes.

Goal:
Detect governance drift, missing artifacts, premature expansion, and repository inconsistency early.

---

## Repository Memory Validation

Verify:

- MIGRATION_SNAPSHOT checked
- WORKFLOW_LOG checked
- relevant registry/index checked
- REPO_MEMORY_STANDARD followed
- WORKFLOW_ENFORCEMENT_RULES followed

If Graphify exists:
- GRAPH_REPORT checked before raw repository exploration

---

## Workflow Structure Validation

Verify:

- FULL_PACKET or COMPACT_PACKET selected correctly
- required artifacts exist
- review artifact exists
- handoff context exists
- state labels exist
- next step explicit

---

## Governance Validation

Verify:

- generated state not presented as executed
- no fake execution claims
- governance documents consistent
- workflow respects current project phase
- architectural decisions documented

---

## Scope Validation

Verify:

- no premature runtime expansion
- no backend outside approved phase
- no automation outside approved phase
- no orchestration engine outside approved phase
- no uncontrolled mass artifact generation

---

## Repository Update Validation

Check whether updates are needed for:

- WORKFLOW_LOG
- MIGRATION_SNAPSHOT
- registry/index files
- review files
- Graphify artifacts if applicable

---

## Workflow Quality Validation

Verify:

- workflow understandable by another agent
- deterministic structure maintained
- handoff quality sufficient
- risks documented
- unresolved questions explicit

---

## Escalation Rule

If major inconsistency or governance drift detected:

- stop expansion
- create review artifact
- update workflow log
- document decision before continuing

---

## Current Policy

Current phase:
Document-first AI Skill Infrastructure.

Priority:
Governance stability before runtime complexity.

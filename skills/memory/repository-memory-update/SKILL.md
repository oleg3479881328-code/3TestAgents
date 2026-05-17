---
name: repository-memory-update
description: Synchronize durable repository memory after verified execution, review, or architectural decisions.
category: memory
status: candidate
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - verified_execution_or_review
  - repository_context
  - workflow_artifacts
outputs:
  - workflow_log_updates
  - migration_snapshot_updates
  - reusable_patterns
  - ckl_candidates
  - locked_decisions
  - repository_memory_changes
safety_level: medium
source: internal
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Synchronize durable repository memory after verified work is completed.

This skill exists to prevent:
- memory loss between chats;
- undocumented decisions;
- missing reusable patterns;
- repository drift;
- knowledge trapped in temporary conversations;
- missing migration continuity;
- governance inconsistency.

Repository memory is treated as the source of truth, not transient chat context.

# Core Principle

Verified work must become durable repository memory.

If important execution, decisions, risks, lessons, or reusable patterns are not persisted, the system loses intelligence over time.

# When to Use

Use this skill after:
- verified implementation execution;
- architecture approval;
- workflow completion;
- major review outcome;
- reusable pattern discovery;
- important governance decisions;
- migration preparation.

Do not use this skill when:
- work is still speculative;
- execution was rejected;
- no durable information was produced;
- the result is not yet verified.

# Repository Memory Layers

## 1. WORKFLOW_LOG.md

Purpose:
Execution memory.

Tracks:
- what actually happened;
- important execution results;
- risks;
- blockers;
- lessons learned;
- important review outcomes.

## 2. MIGRATION_SNAPSHOT.md

Purpose:
Continuation memory.

Tracks:
- current state;
- locked decisions;
- confirmed architecture direction;
- restrictions;
- next recommended step.

## 3. knowledge-library/

Purpose:
Reusable intelligence memory.

Stores:
- reusable patterns;
- anti-patterns;
- workflow techniques;
- architecture lessons;
- governance practices.

## 4. skills/registry.md

Purpose:
Skill lifecycle memory.

Tracks:
- skill status;
- review state;
- promotion readiness;
- deprecation candidates.

# Hard Rules

The memory update process must:
- distinguish verified facts from assumptions;
- preserve repository continuity;
- update only relevant memory layers;
- avoid duplicate memory entries;
- preserve decision history;
- preserve governance boundaries;
- separate execution from interpretation.

The process must not:
- invent repository history;
- mark unverified work as complete;
- overwrite locked decisions silently;
- promote temporary ideas into durable memory;
- create broad memory noise.

# Workflow

## 1. Input Validation

Confirm the following exist:
- verified execution or approved review;
- execution report or review artifact;
- repository context;
- relevant decision references.

If verification is missing:
stop.

Unverified work must not enter durable memory.

## 2. Extract Durable Information

Identify:
- important execution outcomes;
- locked decisions;
- reusable patterns;
- anti-patterns;
- repository risks;
- governance lessons;
- future follow-up requirements.

Ignore:
- temporary brainstorming;
- speculative thoughts;
- non-actionable discussion noise.

## 3. Update WORKFLOW_LOG.md

Record:
- what changed;
- why it changed;
- review outcome;
- important blockers;
- important risks;
- execution status.

The workflow log must remain concise and chronological.

## 4. Update MIGRATION_SNAPSHOT.md

Update only:
- current verified state;
- confirmed decisions;
- active constraints;
- current architecture direction;
- next recommended step.

Never overload migration snapshots with implementation details.

## 5. Extract CKL Candidates

Identify reusable knowledge candidates.

Examples:
- workflow pattern;
- architecture pattern;
- governance rule;
- anti-hallucination technique;
- repository structure improvement;
- execution protocol.

For each candidate include:
- title;
- usefulness;
- portability;
- implementation effort;
- risk;
- suggested category.

## 6. Locked Decision Synchronization

Record decisions that should become durable.

Each locked decision must include:
- Decision ID;
- summary;
- rationale;
- scope;
- status.

Do not silently override prior locked decisions.

## 7. Skill Lifecycle Updates

If the workflow affects a skill:
- update registry status;
- update review state;
- identify promotion readiness;
- identify deprecation risk.

## 8. Final Memory Synchronization Summary

Summarize:
- what memory changed;
- what was intentionally not persisted;
- follow-up memory tasks.

# Output Format

Use this exact structure:

## Repository Memory Update Summary

- Source artifact:
- Verification status:
- Memory update status:
- Main outcome:

## WORKFLOW_LOG Updates

| Entry | Reason | Importance |
|---|---|---|
| TBD | TBD | low/medium/high |

## MIGRATION_SNAPSHOT Updates

| Section | Update | Reason |
|---|---|---|
| TBD | TBD | TBD |

## Locked Decisions

| Decision ID | Decision | Scope | Status |
|---|---|---|---|
| TBD | TBD | TBD | locked/proposed |

## CKL Candidates

| Candidate | Usefulness | Portability | Risk | Suggested Category |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

## Reusable Patterns

| Pattern | Why Reusable | Suggested Destination |
|---|---|---|
| TBD | TBD | TBD |

## Anti-Patterns

| Anti-Pattern | Risk | Mitigation |
|---|---|---|
| TBD | TBD | TBD |

## Skill Lifecycle Findings

| Skill | Suggested Action | Reason |
|---|---|---|
| TBD | TBD | TBD |

## Information Intentionally Not Persisted

| Information | Reason |
|---|---|
| TBD | TBD |

## Final Synchronization Result

One of:
- MEMORY_UPDATED
- MEMORY_UPDATED_WITH_WARNINGS
- MEMORY_UPDATE_BLOCKED

Reason:
- TBD

Next action:
- TBD

# Governance Rules

Never:
- store speculative information as fact;
- persist rejected execution results;
- duplicate memory across layers unnecessarily;
- overwrite locked decisions silently;
- pollute migration snapshots with noise;
- convert brainstorming into repository truth without verification.

# Failure Modes

Possible failures:
- repository memory becomes noisy;
- duplicate memory entries;
- migration snapshots become bloated;
- execution recorded before verification;
- reusable patterns lost;
- governance decisions undocumented;
- temporary discussion treated as durable knowledge.

# Validation Checklist

Before finalizing:
- source artifact verified;
- durable information extracted;
- workflow log updates identified;
- migration updates identified;
- reusable patterns extracted;
- locked decisions synchronized;
- speculative information excluded;
- next step singular and explicit.

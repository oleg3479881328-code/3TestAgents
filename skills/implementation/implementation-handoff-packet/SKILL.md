---
name: implementation-handoff-packet
description: Create deterministic execution packets for handing architecture or specifications to Codex or another implementation agent.
category: implementation
status: candidate
target_agent: codex
compatibility:
  - codex
  - chatgpt
  - claude
inputs:
  - approved_design_or_specification
  - repository_context
  - intended_execution_scope
outputs:
  - execution_packet
  - acceptance_criteria
  - execution_report_contract
  - rollback_notes
  - reviewer_checklist
safety_level: medium
source: internal
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Create a deterministic implementation handoff packet between an Architect Agent and Codex or another implementation agent.

This skill exists to prevent:
- vague Codex prompts;
- uncontrolled repository edits;
- scope drift;
- fake completion claims;
- missing acceptance criteria;
- missing rollback notes;
- implementation without governance context.

The output of this skill is an execution contract, not a discussion prompt.

# When to Use

Use this skill when:
- an approved design must be implemented;
- Codex needs a precise execution packet;
- repository files may be changed;
- acceptance criteria must be explicit;
- implementation work must be reviewable;
- a task is too risky for a casual prompt.

Do not use this skill when:
- the design is not approved;
- the task is still in brainstorming;
- no implementation is intended;
- the user only needs explanation or analysis.

# Operating Model

Architect Agent thinks.

Codex executes.

Reviewer verifies.

Repository memory records durable outcomes.

The handoff packet is the boundary between thinking and execution.

# Hard Rules

The packet must:
- be specific;
- define exact scope;
- list allowed files or file areas;
- list forbidden changes;
- define acceptance criteria;
- define execution report format;
- separate generated state from executed state;
- require Codex to report blockers instead of guessing;
- require Codex to preserve repository invariants.

The packet must not:
- ask Codex to redesign the system;
- ask Codex to infer missing architecture;
- allow unrelated cleanup;
- allow broad refactoring without explicit approval;
- imply completion before verification;
- hide assumptions.

# Required Inputs

Before creating a packet, confirm these are available:

- approved goal;
- source design or specification;
- repository path or repository name;
- intended files or areas;
- constraints;
- acceptance criteria;
- known risks;
- expected execution report.

If critical input is missing, stop and request the missing input.

# Packet Types

## 1. FILE_CREATE

Use when Codex must create one or more new files.

## 2. FILE_UPDATE

Use when Codex must modify existing files.

## 3. REFACTOR_LIMITED

Use for tightly scoped refactoring.

## 4. TEST_ADD_OR_UPDATE

Use for tests only.

## 5. DOC_UPDATE

Use for documentation-only changes.

## 6. VALIDATION_ONLY

Use when Codex must inspect, run checks, or report without editing.

# Output Format

Use this exact format for every packet.

## IMPLEMENTATION HANDOFF PACKET

### Packet ID

`IHP-YYYYMMDD-NNN`

### Packet Type

One of:
- FILE_CREATE
- FILE_UPDATE
- REFACTOR_LIMITED
- TEST_ADD_OR_UPDATE
- DOC_UPDATE
- VALIDATION_ONLY

### Target Executor

- Codex in VS Code

### Source Decision / Design

- Source artifact:
- Related Decision IDs:
- Review status:

### Objective

One clear implementation objective.

### Scope

Allowed work:
- TBD

Out of scope:
- TBD

### Repository Context

Repository:
- TBD

Relevant existing files:
- TBD

Relevant standards:
- TBD

### Files Allowed To Change

| Path | Allowed Action | Notes |
|---|---|---|
| TBD | create/update/delete/read-only | TBD |

### Forbidden Changes

Codex must not:
- change unrelated files;
- redesign architecture;
- rename public concepts unless explicitly required;
- introduce new dependencies without explicit approval;
- remove governance or memory rules;
- claim completion without verification;
- create broad refactors outside the packet scope.

### Implementation Instructions

Step-by-step execution instructions:

1. TBD
2. TBD
3. TBD

### Acceptance Criteria

The task is acceptable only if:

- TBD

### Validation Commands / Checks

Run if available:

- TBD

If commands cannot be run, Codex must state why.

### Logging / Memory Requirements

Codex must report:
- files changed;
- summary of changes;
- validation performed;
- validation not performed;
- blockers;
- assumptions made;
- follow-up risks.

If repository workflow requires updating logs, Codex must update only the specified log files.

### Rollback Notes

Rollback strategy:
- TBD

Files to revert if failed:
- TBD

### Execution Report Contract

Codex must respond using this format:

## EXECUTION REPORT

### Status

One of:
- completed
- completed_with_warnings
- blocked
- failed

### Files Changed

| Path | Action | Summary |
|---|---|---|
| TBD | TBD | TBD |

### Validation Performed

- TBD

### Validation Not Performed

- TBD

### Blockers

- TBD

### Assumptions Made

- TBD

### Risks / Follow-Up

- TBD

### Ready For Review

Yes / No

# Codex Communication Rules

Use direct execution language.

Good:
- Read these files first.
- Modify only these files.
- Do not redesign.
- If blocked, stop and report.
- Return the execution report only after changes are made or blocked.

Bad:
- Improve the system.
- Make it better.
- Refactor as needed.
- Use your judgment broadly.
- Update anything relevant.

# Execution State Rules

The packet must distinguish:

## Generated State

The handoff packet has been created.

No repository change has happened yet.

## Executed State

Codex has actually changed files and reported results.

## Verified State

A reviewer or validation process has confirmed the result.

Never say implemented when only generated.

Never say verified when only executed.

# Reviewer Checklist

After Codex returns an execution report, Reviewer must check:

- Did Codex stay inside scope?
- Were only allowed files changed?
- Were forbidden changes avoided?
- Were acceptance criteria met?
- Were validations run or clearly skipped?
- Were assumptions documented?
- Is rollback clear?
- Is the result ready to commit or merge?

# Failure Modes

Possible failures:
- packet too broad;
- missing file list;
- missing acceptance criteria;
- Codex redesigns instead of executes;
- Codex changes unrelated files;
- Codex claims success without validation;
- user confuses generated packet with executed work;
- reviewer approves without checking changed files.

# Validation Checklist

Before finalizing a handoff packet:
- Packet ID exists;
- packet type is selected;
- objective is singular;
- scope is explicit;
- out-of-scope is explicit;
- files allowed to change are listed;
- forbidden changes are listed;
- acceptance criteria are testable;
- validation checks are included or marked unavailable;
- execution report contract is included;
- rollback notes are included;
- generated/executed/verified states are not confused.

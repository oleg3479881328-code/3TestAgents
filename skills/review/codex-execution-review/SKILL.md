---
name: codex-execution-review
description: Validate Codex execution results against the original implementation handoff packet before accepting repository changes.
category: review
status: candidate
target_agent: tool-neutral
compatibility:
  - codex
  - chatgpt
  - claude
inputs:
  - implementation_handoff_packet
  - execution_report
  - changed_files_or_diff
outputs:
  - execution_review
  - scope_drift_analysis
  - acceptance_validation
  - governance_findings
  - final_execution_verdict
safety_level: medium
source: internal
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Review Codex execution results after implementation work and before repository acceptance, merge, promotion, or memory persistence.

This skill exists to prevent:
- fake completion claims;
- hidden scope drift;
- unrelated repository mutations;
- silent architectural rewrites;
- invalid acceptance claims;
- governance violations;
- unsafe merges;
- broken repository memory.

# Core Principle

Execution is not verification.

Codex may:
- misunderstand scope;
- skip validation;
- modify unrelated files;
- partially complete work;
- silently change architecture;
- claim success without proof.

Therefore every execution must be reviewed.

# When to Use

Use this skill after:
- Codex modifies repository files;
- an execution report is returned;
- a pull request or commit is ready for review;
- implementation work may affect repository behavior;
- acceptance criteria must be verified.

Do not use this skill when:
- no repository changes occurred;
- the task was analysis-only;
- no execution packet exists;
- execution never happened.

# Required Inputs

The review requires:
- original implementation handoff packet;
- Codex execution report;
- changed files or diff;
- acceptance criteria;
- execution scope.

If any required input is missing, stop and report the missing artifact.

# Review Responsibilities

The reviewer must determine:

1. Did Codex stay inside scope?
2. Were only allowed files changed?
3. Were forbidden changes avoided?
4. Were acceptance criteria satisfied?
5. Were validations actually run?
6. Are execution claims evidence-backed?
7. Is rollback possible?
8. Is the result safe for repository acceptance?
9. Did Codex silently redesign architecture?
10. Did Codex preserve repository governance?

# Workflow

## 1. Packet Validation

Read the original implementation handoff packet.

Extract:
- Packet ID;
- packet type;
- objective;
- allowed files;
- forbidden changes;
- acceptance criteria;
- validation expectations.

## 2. Execution Report Validation

Read the Codex execution report.

Check:
- claimed status;
- changed files;
- validations claimed;
- blockers;
- assumptions;
- follow-up risks.

If the report is incomplete, mark it as governance failure.

## 3. File Scope Review

Compare changed files against allowed files.

Classify each file:
- allowed;
- unexpected but acceptable;
- out-of-scope;
- governance risk.

Unexpected changes require explanation.

Out-of-scope changes may block acceptance.

## 4. Acceptance Criteria Validation

Check every acceptance criterion individually.

Each criterion must be marked:
- confirmed;
- partially_confirmed;
- unverified;
- failed.

Never treat absence of evidence as success.

## 5. Validation Review

Check whether validations actually happened.

Examples:
- tests run;
- lint run;
- startup check;
- build validation;
- repository structure validation.

If validations were skipped:
- determine whether that was acceptable;
- record the risk.

## 6. Scope Drift Scan

Detect:
- unrelated refactors;
- cleanup outside scope;
- renamed concepts;
- architecture rewrites;
- hidden dependency additions;
- repository structure mutation.

Classify severity:
- low;
- medium;
- high;
- critical.

## 7. Governance Review

Check:
- repository invariants;
- workflow rules;
- memory rules;
- registry consistency;
- migration safety;
- logging obligations.

## 8. Rollback Safety Review

Determine:
- can the change be reverted safely;
- are rollback notes sufficient;
- are touched files isolated enough.

## 9. Final Verdict

Allowed verdicts:

### ACCEPT_EXECUTION

Use only when:
- scope respected;
- acceptance criteria satisfied;
- governance preserved;
- validations acceptable;
- no blocking drift exists.

### ACCEPT_WITH_WARNINGS

Use when:
- implementation mostly succeeds;
- non-critical risks remain;
- follow-up work is needed.

### REQUIRE_REVISION

Use when:
- implementation direction is correct;
- blockers are fixable;
- repository should not yet accept the result.

### REJECT_EXECUTION

Use when:
- scope drift is severe;
- acceptance criteria failed;
- governance violated;
- execution claims are unreliable;
- repository safety is compromised.

# Output Format

Use this exact structure:

## Execution Review Summary

- Packet ID:
- Reviewed execution:
- Overall verdict:
- Main reason:

## Scope Review

| File | Status | Notes |
|---|---|---|
| TBD | allowed/out-of-scope/governance-risk | TBD |

## Acceptance Criteria Validation

| Criterion | Status | Evidence |
|---|---|---|
| TBD | confirmed/partial/unverified/failed | TBD |

## Validation Review

| Validation | Status | Notes |
|---|---|---|
| TBD | performed/skipped/unverified | TBD |

## Scope Drift Findings

| Finding | Severity | Required Action |
|---|---|---|
| TBD | TBD | TBD |

## Governance Findings

| Finding | Severity | Required Action |
|---|---|---|
| TBD | TBD | TBD |

## Rollback Safety

- Rollback confidence:
- Rollback concerns:
- Isolation quality:

## Execution Risks

| Risk | Impact | Mitigation |
|---|---|---|
| TBD | TBD | TBD |

## Required Corrections

| Correction | Blocking | Owner |
|---|---|---|
| TBD | yes/no | TBD |

## Final Execution Verdict

One of:
- ACCEPT_EXECUTION
- ACCEPT_WITH_WARNINGS
- REQUIRE_REVISION
- REJECT_EXECUTION

Reason:
- TBD

Next action:
- TBD

# Hard Constraints

Do not:
- trust execution claims without evidence;
- approve out-of-scope repository mutations silently;
- confuse generated state with executed state;
- ignore skipped validations;
- rewrite architecture during review;
- treat partial completion as full success;
- merge governance violations into accepted state.

# Reviewer Evidence Rules

Every important review claim must reference:
- changed file;
- execution report statement;
- acceptance criterion;
- validation output;
- repository artifact.

If evidence is missing:
- mark the claim as unverified.

# Failure Modes

Possible failures:
- reviewer trusts Codex blindly;
- reviewer ignores file drift;
- acceptance criteria too vague to validate;
- hidden architecture rewrite passes review;
- governance violations ignored;
- validations claimed but never executed;
- reviewer focuses only on syntax instead of workflow integrity.

# Validation Checklist

Before finalizing review:
- original packet reviewed;
- execution report reviewed;
- changed files checked;
- acceptance criteria validated;
- validation evidence checked;
- governance reviewed;
- rollback assessed;
- scope drift classified;
- verdict selected from allowed values;
- next action singular and explicit.

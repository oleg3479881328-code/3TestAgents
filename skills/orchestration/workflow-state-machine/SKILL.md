---
name: workflow-state-machine
description: Define deterministic workflow states and valid state transitions for repository workflows.
category: orchestration
status: candidate
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - workflow_artifact
  - current_state
  - workflow_context
outputs:
  - state_transition_decision
  - allowed_next_states
  - blocked_transitions
  - workflow_status_summary
safety_level: medium
source: internal
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Define deterministic workflow states and valid transitions for repository workflows.

This skill exists to prevent:
- chaotic workflow progression;
- premature execution;
- skipped review gates;
- invalid repository acceptance;
- memory persistence before verification;
- fake workflow completion.

# Important MVP Rule

This is a lightweight governance layer.

It is not a full BPM engine (business process management engine — движок управления бизнес-процессами).

Keep the state model minimal.

Do not introduce unnecessary workflow bureaucracy.

# Core Principle

Every important workflow has:
- a current state;
- allowed next states;
- blocked transitions.

Invalid transitions must be detected explicitly.

# Standard Workflow States

## draft

Initial raw state.

The workflow exists but has not been clarified.

## clarifying

Requirements and goals are being clarified.

Usually handled by:
- `pre-architecture-brainstorming`

## reviewing

An artifact is being reviewed.

Usually handled by:
- `multi-agent-design-review`
- `codex-execution-review`

## approved

The artifact passed review.

Implementation handoff is now allowed.

## handoff_ready

A deterministic execution packet exists.

Codex execution may begin.

## executing

Codex or another executor is performing work.

## execution_review

Execution results are under verification.

## accepted

Execution passed review and is accepted.

## persisted

Repository memory has been synchronized.

## blocked

The workflow cannot continue until blockers are resolved.

## archived

The workflow is complete and inactive.

# Valid State Transitions

## Allowed

| Current State | Allowed Next States |
|---|---|
| draft | clarifying, archived |
| clarifying | reviewing, blocked |
| reviewing | approved, blocked |
| approved | handoff_ready, archived |
| handoff_ready | executing, blocked |
| executing | execution_review, blocked |
| execution_review | accepted, blocked |
| accepted | persisted, archived |
| persisted | archived |
| blocked | clarifying, reviewing, handoff_ready |

# Invalid Transitions

Examples:
- draft → executing
- clarifying → accepted
- reviewing → persisted
- executing → archived
- handoff_ready → persisted

Invalid transitions must be rejected explicitly.

# Transition Rules

## Review Rule

Execution is forbidden unless the workflow reached:
- approved
or
- handoff_ready

## Verification Rule

Persistence is forbidden before:
- execution_review
- accepted

## Memory Rule

Repository memory updates require:
- verified state
or
- accepted state

## Blocker Rule

If critical blockers exist:
- transition to blocked

Do not silently continue.

# Workflow Types

## Lightweight Workflow

Use minimal states:
- draft
- clarifying
- approved
- archived

Use for:
- documentation-only work;
- simple research;
- small analysis tasks.

## Standard Workflow

Use:
- draft
- clarifying
- reviewing
- approved
- handoff_ready
- executing
- execution_review
- accepted
- persisted

Use for:
- repository implementation work;
- Codex workflows;
- skill creation;
- governance changes.

## High-Risk Workflow

Use full workflow plus:
- blocked
- explicit rollback review
- additional review cycles.

Use for:
- architecture changes;
- orchestration changes;
- runtime changes;
- automation affecting many files.

# Output Format

Use this exact structure:

## Workflow State Summary

- Workflow type:
- Current state:
- Requested transition:
- Transition validity:

## Allowed Next States

| State | Reason |
|---|---|
| TBD | TBD |

## Blocked Transitions

| Transition | Reason |
|---|---|
| TBD | TBD |

## Transition Rules Triggered

| Rule | Result |
|---|---|
| TBD | passed/blocked |

## Recommended Next State

- TBD

## Final Transition Decision

One of:
- TRANSITION_ALLOWED
- TRANSITION_BLOCKED
- MANUAL_REVIEW_REQUIRED

Reason:
- TBD

Next action:
- TBD

# Hard Constraints

Do not:
- allow execution before approval;
- allow persistence before verification;
- silently skip blocked state;
- introduce unnecessary states;
- turn the workflow into enterprise bureaucracy;
- confuse routed state with executed state.

# Anti-Overengineering Rules

Always prefer:
- the smallest valid workflow;
- fewer states;
- fewer gates;
- simpler transitions.

Do not add workflow complexity unless:
- repository risk justifies it;
- governance requires it;
- execution history proves it necessary.

# Failure Modes

Possible failures:
- too many states;
- too many gates;
- workflow paralysis;
- bureaucracy replacing productivity;
- invalid transitions silently accepted;
- state confusion;
- persistence before verification.

# Validation Checklist

Before finalizing:
- current state identified;
- requested transition identified;
- transition validated;
- blocked transitions explained;
- minimal workflow selected;
- unnecessary complexity avoided;
- next action singular and explicit.

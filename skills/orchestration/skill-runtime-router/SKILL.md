---
name: skill-runtime-router
description: Route user requests to the correct skill pipeline and determine the required workflow sequence.
category: orchestration
status: candidate
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - user_request
  - repository_context
  - skill_registry
outputs:
  - routing_decision
  - selected_skills
  - workflow_sequence
  - required_gates
  - next_action
safety_level: medium
source: internal
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Route a user request to the correct skill or skill pipeline.

This skill exists to prevent:
- wrong skill selection;
- skipping review gates;
- premature implementation;
- unnecessary overprocessing;
- missing memory updates;
- chaotic manual workflow selection.

The router is the entry control layer for the AI Skill System.

# Core Principle

Do not run every skill for every task.

Select the smallest correct workflow that satisfies the user request, repository governance, and risk level.

# When to Use

Use this skill when:
- a user request may require multiple skills;
- the correct next skill is unclear;
- the request involves architecture, repository changes, implementation, review, or durable memory;
- a task may need orchestration.

Do not use this skill when:
- the user asks a simple factual question;
- the user explicitly names one skill and no routing is needed;
- the task is purely conversational.

# Routing Inputs

Required:
- user request;
- available skill registry;
- repository context if repository work is involved.

Optional:
- current project phase;
- previous workflow state;
- execution report;
- migration snapshot;
- known constraints.

# Skill Categories

## Research

Use when the request needs external repository analysis, open-source discovery, documentation review, or reusable pattern extraction.

Example skill:
- `github-repository-research`

## Design

Use when the request starts from a raw idea and needs clarification before architecture.

Example skill:
- `pre-architecture-brainstorming`

## Review

Use when an artifact needs critique, validation, contradiction detection, or execution verification.

Example skills:
- `multi-agent-design-review`
- `codex-execution-review`

## Implementation

Use when an approved design needs a deterministic Codex packet.

Example skill:
- `implementation-handoff-packet`

## Memory

Use after verified work to update durable repository memory.

Example skill:
- `repository-memory-update`

## Orchestration

Use to select and order skills.

Example skill:
- `skill-runtime-router`

# Routing Decision Rules

## Raw Idea

If the user gives a vague idea, route to:

1. `pre-architecture-brainstorming`

Do not route directly to implementation.

## Design Needs Review

If a design or pre-architecture specification exists, route to:

1. `multi-agent-design-review`

## Approved Design Needs Codex

If the design is approved and implementation is requested, route to:

1. `implementation-handoff-packet`

## Codex Has Executed

If Codex returned an execution report or files changed, route to:

1. `codex-execution-review`

## Verified Execution Needs Persistence

If execution was accepted, route to:

1. `repository-memory-update`

## External Repository / Open Source Analysis

If the request involves analyzing a GitHub repository or borrowing patterns, route to:

1. `github-repository-research`

Then, if adaptation is requested:

2. `pre-architecture-brainstorming`
3. `multi-agent-design-review`

# Standard Pipelines

## Pipeline A — Raw Idea To Specification

Use for early ideas.

1. `pre-architecture-brainstorming`
2. `multi-agent-design-review`

## Pipeline B — Approved Design To Codex

Use when a design is ready for implementation.

1. `implementation-handoff-packet`
2. Codex execution
3. `codex-execution-review`
4. `repository-memory-update`

## Pipeline C — Full Repository Workflow

Use for significant repository work.

1. `pre-architecture-brainstorming`
2. `multi-agent-design-review`
3. `implementation-handoff-packet`
4. Codex execution
5. `codex-execution-review`
6. `repository-memory-update`

## Pipeline D — Research To Reuse

Use when borrowing from external sources.

1. `github-repository-research`
2. `pre-architecture-brainstorming`
3. `multi-agent-design-review`
4. `implementation-handoff-packet` if implementation is requested

## Pipeline E — Execution Verification Only

Use when Codex already executed something.

1. `codex-execution-review`
2. `repository-memory-update` if accepted

# Gate Rules

## Understanding Gate

Required before design.

Handled by:
- `pre-architecture-brainstorming`

## Review Gate

Required before implementation handoff.

Handled by:
- `multi-agent-design-review`

## Execution Gate

Required before repository acceptance.

Handled by:
- `codex-execution-review`

## Memory Gate

Required after verified execution.

Handled by:
- `repository-memory-update`

# Risk Levels

## Low Risk

Examples:
- documentation-only clarification;
- small registry update;
- analysis-only task.

Minimum routing allowed.

## Medium Risk

Examples:
- new skill creation;
- workflow change;
- repository memory update;
- Codex handoff packet.

Review gate recommended.

## High Risk

Examples:
- architecture change;
- governance change;
- repository structure change;
- automation/orchestration change;
- runtime behavior change.

Full pipeline required unless explicitly overridden.

# Output Format

Use this exact structure:

## Routing Decision

- Request summary:
- Risk level:
- Selected pipeline:
- Main reason:

## Selected Skills

| Order | Skill | Purpose |
|---|---|---|
| 1 | TBD | TBD |

## Required Gates

| Gate | Required | Handled By |
|---|---|---|
| Understanding Gate | yes/no | TBD |
| Review Gate | yes/no | TBD |
| Execution Gate | yes/no | TBD |
| Memory Gate | yes/no | TBD |

## Skipped Skills

| Skill | Reason Skipped |
|---|---|
| TBD | TBD |

## Next Action

One concrete next action.

# Constraints

Do not:
- route directly from vague idea to Codex;
- skip review for high-risk changes;
- run memory update before verification;
- select every skill by default;
- expand scope beyond the user request;
- treat routing as execution;
- claim that routed work has been performed.

# Execution State Rules

Routing creates only a routing decision.

It does not execute the selected skills.

States:
- routed: skill path selected;
- active: selected skill is currently being used;
- executed: selected skill produced its artifact;
- verified: review approved the artifact.

Never confuse these states.

# Failure Modes

Possible failures:
- over-routing simple tasks;
- under-routing risky tasks;
- skipping memory synchronization;
- routing implementation before design is approved;
- treating candidate skills as fully proven;
- losing the user in too many workflow steps.

# Validation Checklist

Before finalizing routing:
- user request summarized;
- risk level assigned;
- selected pipeline justified;
- selected skills listed in order;
- required gates identified;
- skipped skills explained;
- next action is singular and explicit.

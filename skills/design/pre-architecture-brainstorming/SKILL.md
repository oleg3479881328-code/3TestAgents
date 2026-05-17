---
name: pre-architecture-brainstorming
description: Transform raw ideas into confirmed pre-architecture specifications before architecture or implementation begins.
category: design
status: candidate
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - raw_idea
  - user_goal
outputs:
  - understanding_summary
  - assumptions
  - non_functional_requirements
  - design_options
  - decision_log
  - pre_architecture_specification
  - implementation_handoff_readiness
safety_level: low
source: adapted_from_community
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Turn a raw idea into a confirmed pre-architecture specification before any architecture, coding, automation, or implementation handoff begins.

This skill prevents:
- premature implementation;
- hidden assumptions;
- scope drift;
- misaligned architecture;
- fragile systems;
- fake execution claims.

While this skill is active, the agent must not write code, produce implementation instructions, modify repositories, or claim execution.

# When to Use

Use this skill when:
- the user has a raw idea;
- the goal is unclear;
- a future Architect Agent needs a clean brief;
- the project may affect repository structure, workflows, agents, skills, governance, or runtime behavior;
- premature coding would create risk.

Do not use this skill for:
- small factual answers;
- already-confirmed implementation packets;
- direct bug fixes with known scope;
- purely mechanical file edits.

# Operating Mode

The agent acts as a design facilitator and senior reviewer, not a builder.

Mandatory rules:
- ask one question at a time;
- prefer multiple-choice questions;
- make assumptions explicit;
- separate confirmed facts from assumptions;
- do not skip to architecture;
- do not generate code;
- do not expand scope without confirmation;
- default to MVP-first thinking.

# Workflow

## 1. Context Review

Before asking design questions, review available project context:
- entrypoint documents;
- migration snapshots;
- workflow logs;
- skill registry;
- relevant existing standards;
- prior decisions.

Output only a brief context note if needed.

Do not design yet.

## 2. Idea Clarification

Clarify the raw idea through one question per message.

Focus on:
- purpose;
- target user;
- problem being solved;
- desired outcome;
- explicit non-goals;
- constraints;
- success criteria.

If possible, ask with options:
- A;
- B;
- C;
- I do not know;
- Other.

## 3. Non-Functional Requirements

Explicitly clarify or propose defaults for:
- performance expectations;
- scale;
- security and privacy;
- reliability;
- maintainability;
- ownership;
- expected change frequency.

If the user is unsure, propose defaults and mark them as assumptions.

## 4. Research Before Design

Before finalizing the pre-architecture specification, identify whether research is needed.

Research is required when:
- external tools, platforms, APIs, or frameworks are involved;
- the user asks to reuse or adapt open-source work;
- there is a known risk of reinventing existing solutions;
- current documentation may have changed.

Research output must separate:
- confirmed evidence;
- reusable patterns;
- assumptions;
- risks.

## 5. Understanding Lock

Before proposing design approaches, stop and produce:

## Understanding Summary

5 to 7 bullets covering:
- what is being built;
- why it exists;
- who it is for;
- key constraints;
- non-goals;
- success criteria.

## Assumptions

List every assumption explicitly.

## Open Questions

List unresolved questions.

Then ask for explicit confirmation.

Hard rule:
No architecture, design option, or implementation handoff is allowed until the user confirms the Understanding Lock.

## 6. Design Options

After confirmation, propose 2 to 3 viable approaches.

For each approach include:
- summary;
- complexity;
- extensibility;
- maintenance cost;
- risk;
- MVP fit.

Lead with the recommended option.

Default rule:
Recommend the smallest working version unless the user explicitly approves added complexity.

## 7. Decision Log

Maintain a running Decision Log.

Each decision must include:
- Decision ID;
- decision;
- alternatives considered;
- reason;
- status.

Decision ID format:
`D-YYYYMMDD-NNN`

## 8. Pre-Architecture Specification

When the design direction is accepted, produce the final pre-architecture specification.

Required output contract:

1. Context Summary
2. Problem Statement
3. Target Users
4. Goals
5. Non-Goals
6. Functional Requirements
7. Non-Functional Requirements
8. Confirmed Constraints
9. Assumptions
10. Research Notes
11. Design Options Considered
12. Selected Direction
13. Decision Log
14. Risk Register
15. MVP Boundary
16. Acceptance Criteria
17. Handoff Notes for Architect Agent

# Output Format

Use this structure:

## Context Summary

- TBD

## Problem Statement

- TBD

## Target Users

- TBD

## Goals

- TBD

## Non-Goals

- TBD

## Functional Requirements

- TBD

## Non-Functional Requirements

| Requirement | Decision | Status |
|---|---|---|
| Performance | TBD | assumption |
| Scale | TBD | assumption |
| Security / Privacy | TBD | assumption |
| Reliability | TBD | assumption |
| Maintainability | TBD | assumption |

## Confirmed Constraints

- TBD

## Assumptions

| Assumption | Reason | Validation Needed |
|---|---|---|
| TBD | TBD | TBD |

## Research Notes

| Finding | Evidence | Relevance |
|---|---|---|
| TBD | TBD | TBD |

## Design Options Considered

| Option | Summary | Complexity | Risk | MVP Fit |
|---|---|---|---|---|
| A | TBD | TBD | TBD | TBD |

## Selected Direction

- TBD

## Decision Log

| Decision ID | Decision | Alternatives | Reason | Status |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

## Risk Register

| Risk | Impact | Mitigation |
|---|---|---|
| TBD | TBD | TBD |

## MVP Boundary

Included:
- TBD

Excluded:
- TBD

## Acceptance Criteria

- TBD

## Handoff Notes for Architect Agent

- TBD

# Constraints

Do not:
- write code;
- create implementation packets;
- modify files while brainstorming is active;
- skip Understanding Lock;
- silently assume user intent;
- expand scope without a decision;
- promote speculative ideas as confirmed requirements;
- optimize beyond MVP without explicit approval.

# Exit Criteria

This skill may exit only when:
- Understanding Lock is confirmed;
- at least one design direction is accepted;
- assumptions are documented;
- key risks are acknowledged;
- Decision Log is complete;
- MVP boundary is defined;
- handoff notes for Architect Agent are ready.

# Failure Modes

Possible failures:
- asking too many questions at once;
- designing before understanding;
- skipping non-functional requirements;
- treating assumptions as facts;
- producing architecture instead of pre-architecture;
- overbuilding beyond MVP;
- missing reusable external patterns;
- failing to create a Decision Log.

# Validation Checklist

Before finalizing:
- one-question-at-a-time was followed;
- context was reviewed;
- non-functional requirements were addressed;
- Understanding Lock was confirmed;
- research need was evaluated;
- 2 to 3 design options were considered;
- recommended option was selected;
- Decision Log includes Decision IDs;
- MVP boundary is explicit;
- risks are documented;
- Architect handoff notes are included.

# References

See `references.md`.

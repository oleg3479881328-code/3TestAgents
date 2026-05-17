---
name: multi-agent-design-review
description: Review a proposed design or pre-architecture specification through multiple specialist review lenses before implementation handoff.
category: review
status: candidate
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - design_or_pre_architecture_specification
  - user_goal
outputs:
  - review_summary
  - specialist_reviews
  - contradictions
  - risks
  - reusable_patterns
  - required_changes
  - final_recommendation
safety_level: low
source: internal
review_status: reviewed_with_required_improvements
version: 0.1.0
---

# Purpose

Review a proposed design or pre-architecture specification before it is handed to an Architect Agent, Coder-Spec Agent, Codex, or any implementation workflow.

This skill exists to prevent:
- weak specifications;
- hidden contradictions;
- missing research;
- premature implementation;
- scope drift;
- overengineering;
- fake readiness claims;
- loss of reusable patterns.

# When to Use

Use this skill after:
- `pre-architecture-brainstorming` has produced a draft specification;
- an Architect Agent has produced a design;
- a workflow is about to move toward implementation;
- a design affects repository governance, skill lifecycle, agent behavior, or system architecture.

Do not use this skill for:
- trivial factual answers;
- small text edits;
- tasks with no design or specification artifact;
- emergency direct fixes where review would block necessary repair.

# Operating Mode

The agent runs a structured review using multiple review lenses.

This is not a real autonomous swarm.

It is a deterministic multi-lens review model.

Each lens reviews the same artifact from a different responsibility boundary.

Mandatory rules:
- do not write implementation code;
- do not claim execution;
- separate confirmed issues from assumptions;
- identify blockers explicitly;
- preserve MVP-first thinking;
- produce required changes before handoff;
- avoid expanding scope unless the review proves it is necessary.

# Review Lenses

## 1. Architect Lens

Checks:
- architecture clarity;
- component boundaries;
- data flow;
- lifecycle consistency;
- repository structure fit;
- integration with existing standards.

Must answer:
- Is the design structurally coherent?
- Are responsibilities separated?
- Is the design too broad or too vague?

## 2. Reviewer Lens

Checks:
- contradictions;
- missing requirements;
- scope drift;
- fake execution claims;
- unconfirmed assumptions;
- governance violations.

Must answer:
- What blocks this from moving forward?
- What must be corrected before handoff?

## 3. Research Lens

Checks:
- whether external research is needed;
- whether existing open-source patterns should be reviewed;
- whether official documentation is required;
- whether prior art may reduce risk.

Must answer:
- Is the design reinventing something that should be reused?
- Are claims evidence-backed?

## 4. Librarian Lens

Checks:
- reusable patterns;
- decisions worth preserving;
- anti-patterns;
- future CKL candidates;
- registry or documentation updates needed.

Must answer:
- What should be extracted into reusable knowledge?
- What should be added to repository memory?

## 5. MVP Lens

Checks:
- smallest useful version;
- unnecessary complexity;
- optional features disguised as requirements;
- phased rollout possibility.

Must answer:
- What is the minimum working version?
- What should be explicitly excluded for now?

# Workflow

## 1. Input Validation

Confirm the input artifact exists and is reviewable.

Required input must include at least:
- goal;
- proposed design or specification;
- assumptions or constraints;
- intended next step.

If the input is not reviewable, stop and request the missing artifact.

## 2. Context Check

Check relevant repository context when available:
- `docs/PROJECT_ENTRYPOINT.md`;
- `docs/MIGRATION_SNAPSHOT.md`;
- `docs/REPO_MEMORY_STANDARD.md`;
- `docs/WORKFLOW_ENFORCEMENT_RULES.md`;
- `docs/WORKFLOW_ARTIFACT_STANDARD.md`;
- `skills/registry.md`;
- related skill files.

## 3. Specialist Reviews

Run each review lens separately.

For every lens, produce:
- verdict;
- findings;
- blockers;
- required changes;
- optional improvements.

Verdict values:
- pass;
- pass_with_changes;
- blocked.

## 4. Contradiction Scan

Identify contradictions between:
- goals and requirements;
- requirements and constraints;
- design and MVP boundary;
- assumptions and confirmed facts;
- proposed handoff and repository governance.

## 5. Risk Register

List risks using this model:
- risk;
- impact;
- likelihood;
- mitigation;
- owner or next responsible role.

## 6. Required Changes

Separate required changes from optional improvements.

Required changes are blockers for handoff.

Optional improvements must not block MVP unless they affect correctness, safety, or governance.

## 7. Final Recommendation

Return one of three outcomes:

## APPROVE_FOR_HANDOFF

Use only when:
- no blockers remain;
- assumptions are documented;
- MVP boundary is clear;
- risks are acceptable.

## REVISE_BEFORE_HANDOFF

Use when:
- design is directionally correct;
- required changes are limited;
- no full redesign is needed.

## BLOCK_HANDOFF

Use when:
- major requirements are missing;
- assumptions dominate the design;
- contradictions are serious;
- implementation would likely create bad architecture or wasted work.

# Output Format

Use this exact structure:

## Review Summary

- Artifact reviewed:
- Intended next step:
- Overall verdict:
- Main reason:

## Specialist Reviews

### Architect Lens

- Verdict:
- Findings:
- Blockers:
- Required Changes:
- Optional Improvements:

### Reviewer Lens

- Verdict:
- Findings:
- Blockers:
- Required Changes:
- Optional Improvements:

### Research Lens

- Verdict:
- Findings:
- Blockers:
- Required Changes:
- Optional Improvements:

### Librarian Lens

- Verdict:
- Findings:
- Blockers:
- Required Changes:
- Optional Improvements:

### MVP Lens

- Verdict:
- Findings:
- Blockers:
- Required Changes:
- Optional Improvements:

## Contradictions

| Contradiction | Evidence | Severity | Required Fix |
|---|---|---|---|
| TBD | TBD | TBD | TBD |

## Risk Register

| Risk | Impact | Likelihood | Mitigation | Owner |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

## Required Changes Before Handoff

| Change | Reason | Owner | Blocking |
|---|---|---|---|
| TBD | TBD | TBD | yes/no |

## Optional Improvements

| Improvement | Value | Defer? |
|---|---|---|
| TBD | TBD | yes/no |

## Reusable Patterns / CKL Candidates

| Pattern | Why Useful | Suggested Destination |
|---|---|---|
| TBD | TBD | TBD |

## Final Recommendation

One of:
- APPROVE_FOR_HANDOFF
- REVISE_BEFORE_HANDOFF
- BLOCK_HANDOFF

Reason:
- TBD

Next action:
- TBD

# Constraints

Do not:
- produce implementation code;
- rewrite the whole design unless explicitly requested;
- create new scope as a hidden requirement;
- mark speculative findings as confirmed;
- ignore missing research when external systems are involved;
- approve a handoff with unresolved blockers;
- treat optional improvements as MVP blockers.

# Exit Criteria

The review is complete only when:
- every review lens has a verdict;
- contradictions are scanned;
- risks are documented;
- required changes are separated from optional improvements;
- reusable patterns are identified;
- final recommendation is one of the allowed outcomes;
- next action is explicit and singular.

# Failure Modes

Possible failures:
- pretending multiple agents executed real work;
- reviewing too generally;
- missing governance violations;
- approving vague specs;
- blocking MVP due to unnecessary perfectionism;
- failing to identify reusable knowledge;
- mixing research assumptions with confirmed evidence.

# Validation Checklist

Before finalizing:
- input artifact was reviewable;
- all five lenses were applied;
- no implementation code was produced;
- blockers were explicit;
- optional improvements were separated;
- MVP boundary was protected;
- research gaps were identified;
- CKL candidates were listed;
- final recommendation is clear.

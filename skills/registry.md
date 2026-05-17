# AI Skill System — Skill Registry

## Purpose

This registry tracks all known skills inside the AI Skill System.

The registry exists to prevent:
- duplicate skills;
- prompt dump degeneration;
- lost workflows;
- unclear lifecycle state;
- missing review status;
- uncontrolled repository growth.

## Registry Rules

Every skill must:
- appear in this registry;
- have a unique name;
- have a lifecycle status;
- have a review status;
- define compatibility;
- define source attribution.

A skill that does not exist in this registry is not considered part of the active system.

## Lifecycle States

Allowed statuses:
- draft
- candidate
- reviewed
- active
- deprecated
- retired

## Review States

Allowed review states:
- not_reviewed
- reviewed_with_required_improvements
- approved
- rejected

## Registered Skills

| Skill Name | Category | Status | Review Status | Compatibility | Version | Path |
|---|---|---|---|---|---|---|
| github-repository-research | research | candidate | reviewed_with_required_improvements | chatgpt, codex, claude | 0.1.1 | skills/research/github-repository-research/SKILL.md |
| pre-architecture-brainstorming | design | candidate | reviewed_with_required_improvements | chatgpt, codex, claude | 0.1.0 | skills/design/pre-architecture-brainstorming/SKILL.md |
| multi-agent-design-review | review | candidate | reviewed_with_required_improvements | chatgpt, codex, claude | 0.1.0 | skills/review/multi-agent-design-review/SKILL.md |
| implementation-handoff-packet | implementation | candidate | reviewed_with_required_improvements | codex, chatgpt, claude | 0.1.0 | skills/implementation/implementation-handoff-packet/SKILL.md |
| codex-execution-review | review | candidate | reviewed_with_required_improvements | codex, chatgpt, claude | 0.1.0 | skills/review/codex-execution-review/SKILL.md |
| repository-memory-update | memory | candidate | reviewed_with_required_improvements | chatgpt, codex, claude | 0.1.0 | skills/memory/repository-memory-update/SKILL.md |

## Future Registry Fields

Possible future fields:
- owner
- maintainer
- tags
- dependencies
- adapter support
- validation score
- last reviewed date
- review history
- usage count
- risk level

## Registry Governance

### Adding a Skill

Before adding a new skill:
1. search existing registry entries;
2. check for overlapping functionality;
3. verify lifecycle state;
4. attach references;
5. define review status.

### Promoting a Skill

A skill cannot move to `active` without:
- completed review;
- evidence-backed workflow;
- validation checklist;
- stable scope boundary.

### Deprecating a Skill

A skill should be deprecated if:
- replaced by a better version;
- unsafe;
- unmaintained;
- too broad;
- duplicated.

## MVP Decision

The registry is Markdown-first.

Future versions may use YAML, JSON, SQLite, or semantic indexing, but Markdown remains the current source of truth.

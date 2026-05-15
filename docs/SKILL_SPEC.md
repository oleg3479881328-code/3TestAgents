# AI Skill System — Skill Specification

## 1. Definition

A skill is a focused reusable AI workflow stored as a folder with a primary `SKILL.md` file and source references.

A skill is not just a prompt. A skill is an operational unit that defines when to use it, what inputs it needs, what outputs it produces, what steps it follows, what constraints it must obey, and how it can be validated.

## 2. Skill Folder Structure

Required structure:

```text
skills/<category>/<skill-name>/
  SKILL.md
  references.md
```

Optional future structure:

```text
skills/<category>/<skill-name>/
  SKILL.md
  references.md
  examples/
  validation/
  assets/
  scripts/
```

## 3. Required Files

### SKILL.md

Primary instruction file for the skill.

### references.md

Source links, inspiration references, adapted patterns, and attribution notes.

## 4. Optional Files

### examples/

Example inputs and outputs.

### validation/

Manual or future automated validation checks.

### assets/

Images, diagrams, or supporting files.

### scripts/

Future executable helpers. Not allowed in the document-first MVP unless explicitly approved later.

## 5. Required Metadata

Every `SKILL.md` must begin with YAML frontmatter.

Minimum fields:

```yaml
---
name: example-skill-name
description: Short description of what the skill does.
category: research
status: draft
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - input_name
outputs:
  - output_name
safety_level: low
source: internal
review_status: not_reviewed
version: 0.1.0
---
```

## 6. Required Body Sections

Every skill must include:

1. Purpose
2. When to Use
3. Inputs
4. Outputs
5. Workflow
6. Constraints
7. Failure Modes
8. Validation Checklist
9. References

## 7. Naming Rules

Skill names must:
- use lowercase;
- use hyphen-separated words;
- describe one task;
- avoid vague names like `helper`, `assistant`, `agent`, or `general`.

Good:
`github-repository-research`

Bad:
`super-agent`

## 8. Quality Rules

A skill must:
- have a narrow task boundary;
- define required inputs;
- define expected outputs;
- list constraints;
- list failure modes;
- include references when adapted from external work;
- avoid fake execution claims;
- remain tool-neutral unless intentionally written as an adapter.

## 9. What Is Not a Skill

Not a skill:
- a random prompt;
- a vague agent persona;
- a one-off chat answer;
- an unreviewed instruction dump;
- a broad universal assistant trying to do everything.

## 10. MVP Decision

The first skill format is Markdown-first and tool-neutral.

The source of truth is the internal `SKILL.md` format. Claude, Codex, and ChatGPT-specific versions are future adapters, not the core format.

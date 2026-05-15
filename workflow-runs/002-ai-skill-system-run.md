# Workflow Run 002 — AI Skill System

## 0. Run Status

Status: in-progress

Execution state:
- This file is a real workflow run, not a template.
- No code has been written.
- No implementation has been tested.
- No automation has been added.
- Current stage: Coder-Spec completed.

Purpose:
Run the first real document-first agent workflow for the AI Skill System concept.

---

## 1. Input Idea

### Raw Idea

AI Skill System

### Problem

Modern AI tools can perform powerful work, but users often lose good workflows because the process stays inside temporary chats.

Good prompts, repeated workflows, useful agent behaviors, research patterns, artifact formats, and execution rules are not captured as reusable operational units.

As a result:
- useful discoveries are lost;
- successful workflows are hard to repeat;
- different agents behave inconsistently;
- project knowledge becomes scattered;
- Codex, ChatGPT, Claude, and other AI tools are not coordinated through a stable skill layer.

### Desired Result

Create a structured AI Skill System that can capture, organize, improve, and reuse strong AI workflows as portable skills.

The system should help turn successful AI interactions into repeatable skill files, agent instructions, workflow templates, research methods, output contracts, and reusable project patterns.

### MVP Boundary

The first version is document-first only.

In scope:
- define what an AI skill is;
- define the lifecycle of a skill;
- define repository structure;
- define how skills are discovered, reviewed, stored, reused, and improved;
- define how existing open-source skill repositories can be analyzed and adapted;
- create implementation-ready specifications later, but not code yet.

Out of scope:
- no local runtime;
- no Codex execution;
- no app backend;
- no UI;
- no automation layer;
- no marketplace;
- no production deployment.

---

## 2. Pre-Architect Output

Role:
Pre-Architect

Responsibility:
Convert the raw idea into a structured concept brief.

### Structured Concept Brief

#### Project Name

AI Skill System

#### Target User

Primary target user:
An AI operator who uses ChatGPT, Codex, Claude, local models, GitHub, and project repositories to build repeatable AI-powered workflows.

Secondary target users:
- prompt engineers;
- AI product builders;
- solo founders;
- automation builders;
- agent-system designers;
- developers who want reusable AI workflows.

#### Main Use Case

The user completes a useful AI workflow once, then turns that workflow into a reusable skill.

Example:
A successful conversation about researching GitHub repositories becomes a reusable Research Skill.

Another example:
A good agent specification becomes a reusable Agent Creation Skill.

Another example:
A working review process becomes a reusable Reviewer Skill.

#### Core Value

The system converts temporary AI work into permanent reusable operational knowledge.

Core value:
- less repeated thinking;
- less prompt drift;
- more consistent agent behavior;
- faster project creation;
- easier reuse of strong external patterns;
- stronger bridge between ChatGPT, Codex, GitHub, and future automation.

#### Required Inputs

The system should accept:
- raw chat conversations;
- successful prompts;
- agent instructions;
- GitHub repository links;
- open-source skill examples;
- workflow descriptions;
- project rules;
- reusable output formats;
- user corrections and lessons learned.

#### Required Outputs

The system should produce:
- skill files;
- workflow templates;
- agent instruction blocks;
- reusable research methods;
- output contracts;
- review checklists;
- project-specific skill libraries;
- global reusable patterns;
- implementation specifications for Codex later.

#### Constraints

Current MVP constraints:
- document-first only;
- GitHub is the source of truth;
- no fake execution claims;
- generated state must be separated from executed state;
- no application code yet;
- no local runtime yet;
- no automation yet;
- one workflow run at a time;
- one artifact at a time;
- reuse-first: search existing strong patterns before inventing from scratch.

#### Open Questions

1. Should the first skill format be optimized for Codex, Claude, ChatGPT, or be tool-neutral?
2. Should skills be stored as Markdown only, or later also as JSON/YAML?
3. Should every skill include tests or validation criteria?
4. Should skills have categories such as research, coding, review, documentation, automation, business, design?
5. Should the system have global skills and project-specific skills separately?

### Pre-Architect Decision

The AI Skill System should start as a document-first repository framework for capturing and reusing AI workflows.

The MVP should not attempt to build software yet.

The first concrete output should be a stable skill specification format and repository structure.

---

## 3. Research Agent Output

Role:
Research Agent

Responsibility:
Search for existing reusable patterns, open-source examples, documentation, and architecture ideas before designing from scratch.

### Search Scope

#### GitHub

Reviewed public skill repositories and catalogs:
- anthropics/skills
- openai/skills
- sickn33/antigravity-awesome-skills
- VoltAgent/awesome-agent-skills
- JayLZhou/Awesome-Agent-Skills

#### Official Documentation

Official or primary references found:
- Anthropic Agent Skills repository and linked Agent Skills specification
- OpenAI Skills Catalog for Codex
- Agent Skills open standard reference

#### Community Sources

Community references found:
- Antigravity Awesome Skills collection
- VoltAgent Awesome Agent Skills catalog
- JayLZhou Awesome Agent Skills research catalog

#### Existing Tools or Products

Existing ecosystem patterns found:
- Claude skills use folder-based skills with SKILL.md files.
- Codex skills use folders of instructions, scripts, and resources.
- Community catalogs organize skills by tool, topic, framework, and task type.
- Research catalogs classify skills by lifecycle: representation, acquisition, retrieval, selection, evolution, and governance.

### Findings

#### Finding 1 — Skill as a folder-based operational unit

Anthropic defines skills as folders containing instructions, scripts, and resources that Claude loads dynamically for specialized tasks. The Anthropic repository also shows a simple creation model: a skill is a folder with a SKILL.md file containing YAML frontmatter and instructions.

Implication for this project:
The AI Skill System should use a folder-based unit as the default mental model.

#### Finding 2 — Skill as reusable capability package for Codex

OpenAI's skills repository defines Agent Skills as folders of instructions, scripts, and resources that AI agents can discover and use for specific tasks. It frames the principle as write once, use everywhere.

Implication for this project:
The AI Skill System should not be Claude-only. It should be tool-neutral first, with compatibility layers for Codex, Claude, ChatGPT, and future agents.

#### Finding 3 — Community catalogs prove the category problem

VoltAgent's catalog contains 1000+ agent skills across official and community sources and explicitly lists compatibility across Claude Code, Codex, Gemini CLI, Cursor, and more.

Implication for this project:
A skill system needs classification, tags, quality markers, compatibility fields, and security review status. A flat folder dump will become garbage quickly.

#### Finding 4 — Research taxonomy gives the lifecycle model

The JayLZhou Awesome-Agent-Skills catalog follows a lifecycle perspective: skill representation, skill acquisition, skill retrieval and selection, skill evolution and governance.

Implication for this project:
The AI Skill System should not only store skills. It must define the full lifecycle: create, review, index, retrieve, use, evaluate, improve, retire.

#### Finding 5 — Brainstorming skill confirms small atomic skills are useful

The antigravity-awesome-skills brainstorming example is a single skill folder with a SKILL.md file.

Implication for this project:
The first MVP skill should be small and atomic, not a giant universal meta-agent.

### Reusable Patterns

#### Pattern 1 — Folder + SKILL.md

Each skill should be a directory with one primary instruction file.

Proposed local convention:
- SKILL.md for the main skill instructions
- README.md only for human-facing explanation if needed
- examples/ for examples
- tests/ or validation/ for future checks
- references.md for source links and attribution

#### Pattern 2 — Metadata frontmatter

Each skill should include machine-readable metadata at the top.

Minimum fields:
- name
- description
- category
- target_agent
- compatibility
- inputs
- outputs
- safety_level
- source
- status

#### Pattern 3 — Lifecycle fields

Every skill should have lifecycle status.

Proposed statuses:
- draft
- candidate
- reviewed
- active
- deprecated
- retired

#### Pattern 4 — Reuse-first research step

Before creating a new skill, the system should search existing skill repositories and extract patterns.

This becomes a permanent rule:
Do not invent a skill from scratch before checking existing examples.

#### Pattern 5 — Tool-neutral core with adapters

The core skill format should be tool-neutral.

Adapters can later generate:
- Claude-compatible skill folders
- Codex-compatible skill folders
- ChatGPT Custom GPT instruction blocks
- project-specific agent prompts

### Research Agent Decision

The AI Skill System should adopt a tool-neutral folder-based skill model inspired by Anthropic and OpenAI, but add stronger lifecycle governance, classification, and review controls.

The MVP should create a first internal skill format before building any runtime.

The next architecture step should define:
- repository structure;
- skill file schema;
- lifecycle model;
- review process;
- compatibility/adaptation strategy;
- first atomic skill candidate.

---

## 4. Architect Output

Role:
Architect

Responsibility:
Design the system or workflow at the architecture level.

### Architecture Summary

The AI Skill System should be a document-first GitHub framework for capturing, reviewing, organizing, and reusing AI workflows as portable skill units.

The MVP is not a runtime, app, backend, UI, marketplace, or automation layer. The MVP is a committed specification set and one first skill candidate.

### Core Architecture

#### Component 1 — Skill Unit

A skill is one focused reusable workflow stored as a folder.

Required files:
- SKILL.md
- references.md

Optional future folders:
- examples/
- validation/
- assets/
- scripts/

#### Component 2 — Skill Registry

A registry lists available skills and their metadata.

MVP form:
Markdown index.

Future form:
YAML, JSON, SQLite, or searchable index.

#### Component 3 — Lifecycle Model

Skill statuses:
- draft
- candidate
- reviewed
- active
- deprecated
- retired

A skill must not become active without review.

#### Component 4 — Review Process

Every skill must be checked for:
- clear task boundary;
- defined inputs;
- defined outputs;
- source attribution;
- compatibility notes;
- failure modes;
- validation checklist;
- no fake execution claims.

#### Component 5 — Adapter Layer

The core skill format stays tool-neutral.

Future adapters can generate:
- Claude-compatible skills;
- Codex-compatible skills;
- ChatGPT Custom GPT instructions;
- project-specific agent prompts.

#### Component 6 — Knowledge Library

The knowledge library stores reusable patterns, rules, and architectural lessons.

Difference:
A skill is an executable workflow instruction.
A knowledge-library record is reusable knowledge that may later become part of a skill.

### Proposed Future Repository Structure

```text
ai-skill-system/
  README.md
  PROJECT_INDEX.md
  docs/
    SKILL_SPEC.md
    LIFECYCLE.md
    REVIEW_PROCESS.md
    COMPATIBILITY_MODEL.md
  skills/
    research/
      github-repository-research/
        SKILL.md
        references.md
        examples/
        validation/
    architecture/
    coding/
    review/
    documentation/
    automation/
    business/
    design/
  adapters/
    claude/
    codex/
    chatgpt/
  workflow-runs/
  knowledge-library/
  logs/
```

### Proposed SKILL.md Minimum Metadata

```yaml
---
name: github-repository-research
description: Research a GitHub repository and extract reusable architecture and workflow patterns.
category: research
status: draft
target_agent: tool-neutral
compatibility:
  - chatgpt
  - codex
  - claude
inputs:
  - repository_url
  - user_goal
outputs:
  - research_summary
  - reusable_patterns
  - risks
  - recommended_next_step
safety_level: low
source: internal
review_status: not_reviewed
version: 0.1.0
---
```

Required body sections:
- Purpose
- When to Use
- Inputs
- Outputs
- Workflow
- Constraints
- Failure Modes
- Validation Checklist
- References

### Data Flow

```text
Raw idea or conversation
  -> Pre-Architect structured concept
  -> Research Agent pattern search
  -> Architect skill-system design
  -> Coder-Spec implementation file tasks
  -> Reviewer quality audit
  -> Librarian reusable pattern extraction
  -> approved skill candidate
```

### State Model

Generated state:
Proposed by an AI agent but not committed.

Committed state:
Written to GitHub.

Reviewed state:
Checked by Reviewer Agent or human reviewer.

Active state:
Approved for reuse.

### First Atomic Skill Candidate

First skill candidate:
`github-repository-research`

Reason:
The AI Skill System depends on analyzing external GitHub repositories before creating or adapting new skills.

Future path:
`skills/research/github-repository-research/SKILL.md`

### Architecture Decision

The AI Skill System must start as a tool-neutral, folder-based, GitHub-managed skill framework.

The next workflow stage should be Coder-Spec Agent Output, but still document-only.

Coder-Spec must define the exact files to create:
- docs/SKILL_SPEC.md
- docs/LIFECYCLE.md
- docs/REVIEW_PROCESS.md
- docs/COMPATIBILITY_MODEL.md
- skills/research/github-repository-research/SKILL.md
- skills/research/github-repository-research/references.md

---

## 5. Coder-Spec Agent Output

Role:
Coder-Spec Agent

Responsibility:
Convert the architecture into implementation-ready file tasks.

Important:
This is still document-first work. This output does not authorize application code, backend code, runtime setup, automation, or local execution.

### Implementation Task Spec

#### Task Title

Create AI Skill System document specification set and first skill candidate.

#### Goal

Create the first committed document set that defines the AI Skill System as a reusable, tool-neutral, folder-based skill framework.

The output should make the next repository state explicit enough that a human or Codex can create the files without inventing structure.

#### Files to Create or Edit

Create these files:

1. `docs/SKILL_SPEC.md`
2. `docs/LIFECYCLE.md`
3. `docs/REVIEW_PROCESS.md`
4. `docs/COMPATIBILITY_MODEL.md`
5. `skills/research/github-repository-research/SKILL.md`
6. `skills/research/github-repository-research/references.md`

Optional later files, not in this task:
- `skills/README.md`
- `skills/registry.md`
- `adapters/README.md`
- `knowledge-library/skill-patterns.md`

#### File 1 — docs/SKILL_SPEC.md

Purpose:
Define what a skill is in this system.

Required sections:
- Definition
- Skill Folder Structure
- Required Files
- Optional Files
- Required Metadata
- Required Body Sections
- Naming Rules
- Quality Rules
- What Is Not a Skill

Minimum decision:
A skill is a focused reusable AI workflow stored as a folder with a primary `SKILL.md` file and source references.

#### File 2 — docs/LIFECYCLE.md

Purpose:
Define lifecycle states and allowed transitions.

Required statuses:
- draft
- candidate
- reviewed
- active
- deprecated
- retired

Required sections:
- Status Definitions
- Transition Rules
- Promotion Criteria
- Deprecation Criteria
- Retirement Criteria
- Generated vs Committed vs Reviewed vs Active State

Minimum decision:
No skill can become active without review.

#### File 3 — docs/REVIEW_PROCESS.md

Purpose:
Define how skills are reviewed before reuse.

Required sections:
- Review Purpose
- Review Checklist
- Required Evidence
- Failure Conditions
- Approval Rules
- Reviewer Output Format

Minimum checklist:
- clear task boundary;
- defined inputs;
- defined outputs;
- source attribution;
- compatibility notes;
- failure modes;
- validation checklist;
- no fake execution claims.

#### File 4 — docs/COMPATIBILITY_MODEL.md

Purpose:
Define tool-neutral core and future adapter targets.

Required sections:
- Tool-Neutral Core
- Claude Compatibility
- Codex Compatibility
- ChatGPT Compatibility
- Project-Specific Agent Compatibility
- Adapter Rules
- Out-of-Scope Runtime Rules

Minimum decision:
The core skill format must remain tool-neutral. Claude, Codex, and ChatGPT outputs are adapters, not the source of truth.

#### File 5 — skills/research/github-repository-research/SKILL.md

Purpose:
Create the first atomic skill candidate.

Required metadata:
- name: github-repository-research
- description: Research a GitHub repository and extract reusable architecture and workflow patterns.
- category: research
- status: draft
- target_agent: tool-neutral
- compatibility: chatgpt, codex, claude
- inputs: repository_url, user_goal
- outputs: research_summary, reusable_patterns, risks, recommended_next_step
- safety_level: low
- source: internal
- review_status: not_reviewed
- version: 0.1.0

Required body sections:
- Purpose
- When to Use
- Inputs
- Outputs
- Workflow
- Constraints
- Failure Modes
- Validation Checklist
- References

Minimum workflow:
1. Read the repository README and structure.
2. Identify the project purpose.
3. Identify reusable architecture or workflow patterns.
4. Separate facts from assumptions.
5. Extract patterns that can be adapted.
6. Produce a short recommendation.

#### File 6 — skills/research/github-repository-research/references.md

Purpose:
List source repositories and inspiration references.

Required references:
- Anthropic Skills repository
- OpenAI Skills repository
- Antigravity Awesome Skills catalog
- VoltAgent Awesome Agent Skills catalog
- JayLZhou Awesome Agent Skills catalog

### Required Behavior

The implementation must:
- create only documentation and skill candidate files;
- keep all files in Markdown;
- avoid app code;
- avoid runtime code;
- avoid automation scripts;
- preserve tool-neutral language;
- mark the first skill as `draft`, not `active`;
- keep source attribution visible.

### Acceptance Criteria

The task is accepted only if:
- all six required files exist;
- `SKILL_SPEC.md` defines the internal skill format;
- `LIFECYCLE.md` defines statuses and transitions;
- `REVIEW_PROCESS.md` defines review checklist and approval rules;
- `COMPATIBILITY_MODEL.md` separates core format from adapters;
- first skill candidate exists at `skills/research/github-repository-research/SKILL.md`;
- first skill candidate status is `draft`;
- no application code is added.

### Forbidden Actions

Do not:
- create backend code;
- create frontend code;
- create scripts;
- create automation;
- install dependencies;
- claim any skill is active before review;
- create multiple skill candidates at once;
- build adapter generators yet.

### Expected Output

A committed documentation-first specification set for the AI Skill System plus one draft skill candidate.

### Coder-Spec Decision

The next executed repository change should create the six documentation/skill files listed above.

This should be done as one small document-only commit.

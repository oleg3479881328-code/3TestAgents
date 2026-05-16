# PROJECT ENTRYPOINT

## Purpose

This file is the universal entry point for starting a NEW project inside the repository operating system.

Any new chat, agent, Codex session, or workflow should begin here.

Goal:
Provide a single high-level explanation of:
- how the multi-agent workflow operates;
- how repository memory works;
- how governance is enforced;
- where the detailed rules live.

---

# 1. Core System Concept

This repository is not a normal prompt collection.

It is a:

`Document-First Multi-Agent Repository Operating System`

The system is designed so AI work does not disappear inside temporary chats.

Instead:
- workflows become reusable artifacts;
- decisions become repository memory;
- reviews become governance;
- knowledge becomes reusable patterns.

The repository is the source of truth.

---

# 2. Multi-Agent Workflow Model

Tasks are processed sequentially through specialized agents.

The system intentionally avoids chaotic autonomous swarms.

Reason:
Sequential workflows reduce:
- hallucination drift;
- scope drift;
- fake execution claims;
- architectural chaos.

---

# 3. Current Agent Roles

## Pre-Architect

Converts raw ideas into structured briefs.

Does NOT:
- write code;
- build architecture;
- create runtime.

---

## Research Agent

Searches for:
- reusable patterns;
- open-source solutions;
- architecture ideas;
- operational lessons.

Core principle:
Reuse First.

---

## Architect

Designs:
- architecture;
- repository structure;
- governance boundaries;
- lifecycle rules;
- workflow contracts.

Does NOT write implementation.

---

## Coder-Spec Agent

Produces:
- implementation-ready specifications;
- repository tasks;
- artifact contracts;
- acceptance criteria.

Does NOT automatically execute runtime work.

---

## Reviewer

Checks for:
- contradictions;
- governance violations;
- scope drift;
- fake execution claims;
- premature expansion.

Reviewer may block expansion.

---

## Librarian

Extracts reusable:
- patterns;
- lessons;
- decisions;
- anti-patterns.

Stores them in the knowledge library.

---

# 4. Repository Memory Model

The repository uses layered memory.

## Main Memory Layers

### MIGRATION_SNAPSHOT.md

Continuation memory.

Used when continuing an existing project.

Contains:
- current state;
- confirmed decisions;
- restrictions;
- next step.

---

### WORKFLOW_LOG.md

Execution memory.

Tracks:
- what was actually done;
- important decisions;
- risks;
- lessons learned.

---

### skills/registry.md

Skill memory.

Tracks:
- known skills;
- lifecycle status;
- review status;
- versions.

---

### knowledge-library/

Reusable knowledge memory.

Stores:
- patterns;
- architectural ideas;
- reusable workflows;
- anti-patterns.

---

### graphify-out/

Optional repository cognition layer.

Purpose:
- repository navigation;
- compressed repository understanding;
- machine-traversable structure.

Graphify is NOT runtime infrastructure.

---

# 5. Workflow Execution Modes

The repository supports two workflow modes.

## FULL_PACKET

For:
- architecture;
- governance;
- reusable systems;
- coordination-heavy work.

Uses deterministic multi-file workflow packets.

---

## COMPACT_PACKET

For:
- small tasks;
- validations;
- lightweight reviews.

Uses lightweight workflow records.

---

# 6. Governance Philosophy

Core principle:

`Governance before runtime.`

The system intentionally delays:
- backend systems;
- orchestration engines;
- automation layers;
- vector databases;
- semantic search;
- mass skill generation.

Reason:
Most AI systems collapse from:
- prompt chaos;
- uncontrolled growth;
- weak memory;
- premature automation.

---

# 7. Current Project Phase

Current phase:
Document-first AI Skill Infrastructure.

Current subphase:
Governance Stabilization.

Priority:
Consistency over expansion speed.

---

# 8. Required Detailed Standards

After reading this file, agents should consult the detailed standards.

## Repository Memory Standard

`docs/REPO_MEMORY_STANDARD.md`

Defines:
- repository memory layers;
- read order;
- state labels;
- Graphify role;
- conflict resolution.

---

## Workflow Enforcement Rules

`docs/WORKFLOW_ENFORCEMENT_RULES.md`

Defines:
- mandatory workflow behavior;
- update obligations;
- forbidden workflow actions.

---

## Workflow Artifact Standard

`docs/WORKFLOW_ARTIFACT_STANDARD.md`

Defines:
- FULL_PACKET;
- COMPACT_PACKET;
- deterministic workflow artifacts.

---

## Workflow Validation Checklist

`docs/WORKFLOW_VALIDATION_CHECKLIST.md`

Defines:
- lightweight governance validation;
- workflow acceptance checks;
- escalation rules.

---

# 9. Entry Rules

## Starting A NEW Project

Start here:

`docs/PROJECT_ENTRYPOINT.md`

## Continuing An EXISTING Project

Start with:

`docs/MIGRATION_SNAPSHOT.md`

---

# 10. Final Principle

Repository memory is more important than chat memory.

The repository must remain:
- deterministic;
- reviewable;
- transferable;
- reusable;
- understandable by future agents.

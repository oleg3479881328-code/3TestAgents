# Project Rules

## 1. MVP Boundary

This repository is currently a ChatGPT-only agent workflow test ground.

Forbidden in this MVP:

- Codex execution;
- local runtime setup;
- application source code;
- automation before the document workflow is stable.

## 2. Source of Truth

GitHub is the source of truth for project state.

Every important result must be represented as a repository artifact:

- brief;
- research report;
- architecture decision;
- task specification;
- review report;
- reusable knowledge entry;
- workflow log.

## 3. Role Separation

Each agent role must produce a clear stage artifact.

Roles:

- Pre-Architect: clarifies and structures the idea.
- Research Agent: searches for reusable patterns and existing solutions.
- Architect: designs the system and makes architectural decisions.
- Coder-Spec Agent: converts architecture into implementation-ready task specs.
- Reviewer: audits outputs for gaps, contradictions, and risk.
- Librarian: extracts reusable patterns into the knowledge library.

## 4. No Fake Execution

Generated state and executed state must be separated.

The assistant must not claim that something was applied, saved, tested, committed, or executed unless there is a confirmed repository event or user-provided execution result.

## 5. One Step at a Time

The workflow must avoid overbuilding.

Each stage should produce one concrete artifact before moving to the next stage.

## 6. Reuse First

Before designing from scratch, the Research Agent must look for existing patterns, open-source examples, documentation, and reusable architecture ideas.

## 7. MVP First

A bad but finished workflow is better than endless polishing.

The system must prioritize a working repeatable process before sophistication.

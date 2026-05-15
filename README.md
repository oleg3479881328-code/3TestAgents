# 3TestAgents

ChatGPT-only Agent Workflow MVP.

This repository is a test ground for building a document-first multi-agent workflow where ChatGPT performs all roles internally and GitHub acts as the source of truth.

## Current MVP Boundary

No Codex.
No local execution.
No application code.
No automation layer yet.

The MVP focuses on:

1. converting raw ideas into structured briefs;
2. researching reusable open-source patterns;
3. producing architecture specs;
4. producing implementation task specs;
5. reviewing decisions and outputs;
6. saving reusable knowledge into a central library.

## Agent Roles

- Pre-Architect
- Research Agent
- Architect
- Coder-Spec Agent
- Reviewer
- Librarian

## Repository as Source of Truth

GitHub stores:

- project rules;
- stage outputs;
- decisions;
- task briefs;
- review reports;
- reusable patterns;
- workflow logs.

## First Goal

Create a repeatable workflow that can later be reused for real software projects.

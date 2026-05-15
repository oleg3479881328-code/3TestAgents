# Pattern — State Separation in AI Systems

## Status

active

## Purpose

Prevent hallucinated execution and operational confusion.

## Pattern

The system must distinguish:
- generated state;
- committed state;
- reviewed state;
- active state.

## Definitions

### Generated State

Content proposed by AI but not committed.

### Committed State

Content written to GitHub or another source of truth.

### Reviewed State

Content checked by reviewer.

### Active State

Content approved for operational reuse.

## Why This Exists

AI systems frequently blur:
- ideas;
- drafts;
- executed work;
- approved work.

This causes:
- fake execution claims;
- operational confusion;
- broken trust;
- repository corruption.

## When to Use

Use this pattern:
- in AI agent systems;
- in workflow orchestration;
- in repository-driven systems;
- in multi-agent pipelines.

## When NOT to Use

Never remove state separation in systems where AI can claim execution.

## Source Workflow

Workflow Run 002 — AI Skill System

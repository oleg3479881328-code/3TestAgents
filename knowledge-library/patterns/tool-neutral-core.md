# Pattern — Tool-Neutral Core

## Status

active

## Purpose

Prevent vendor lock-in.

## Pattern

The internal system format must remain independent from:
- Claude;
- Codex;
- ChatGPT;
- Cursor;
- Gemini CLI;
- any single AI ecosystem.

Environment-specific implementations are adapters, not the source of truth.

## Why This Exists

Vendor-specific architectures become fragile when:
- APIs change;
- tools disappear;
- pricing changes;
- execution models shift.

A tool-neutral core preserves portability.

## When to Use

Use this pattern:
- when designing skill systems;
- when building reusable workflows;
- when designing agent infrastructures;
- when supporting multiple AI ecosystems.

## When NOT to Use

If a system is intentionally locked to one environment for strategic reasons.

## Source Workflow

Workflow Run 002 — AI Skill System

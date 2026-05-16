# Workflow Run Template

## Purpose

This directory contains the canonical deterministic workflow packet structure.

All future workflow runs should follow this template unless an explicit exception is approved.

## Canonical Structure

```text
WORKFLOW_RUN_TEMPLATE/
  00_INPUT.md
  01_BRIEF.md
  02_RESEARCH_REPORT.md
  03_ARCHITECTURE_SPEC.md
  04_CODER_SPEC.md
  05_REVIEW_REPORT.md
  06_LIBRARY_EXTRACT.md
  07_HANDOFF_NOTE.md
```

## Current Policy

The workflow packet structure is governed by:
- `docs/WORKFLOW_ARTIFACT_STANDARD.md`
- `docs/REPO_MEMORY_STANDARD.md`
- `docs/WORKFLOW_ENFORCEMENT_RULES.md`

## Notes

Compact single-file workflow records are still allowed for small tasks, but they must preserve the same logical sections.

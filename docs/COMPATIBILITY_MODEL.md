# AI Skill System — Compatibility Model

## Tool-Neutral Core

The internal skill format is the source of truth.

The core format must remain independent from:
- Claude;
- Codex;
- ChatGPT;
- Cursor;
- Gemini CLI;
- any single vendor ecosystem.

## Adapter Philosophy

Adapters translate the core skill format into environment-specific formats.

Adapters are outputs, not the source of truth.

## Planned Compatibility Targets

### Claude

Future output:
Claude-compatible skill folders.

### Codex

Future output:
Codex-compatible skill folders and execution instructions.

### ChatGPT

Future output:
Custom GPT instruction blocks.

### Project-Specific Agents

Future output:
Repository-specific agent prompts and workflows.

## Adapter Rules

Adapters must:
- preserve original meaning;
- preserve workflow boundaries;
- preserve constraints;
- preserve source attribution.

## Out-of-Scope Rules

Not part of the MVP:
- runtime execution;
- automatic adapter generation;
- orchestration engines;
- semantic search;
- skill marketplaces.

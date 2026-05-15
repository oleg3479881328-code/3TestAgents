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

# Purpose

Research a GitHub repository and extract reusable architecture, workflow, and operational patterns.

# When to Use

Use this skill when:
- analyzing open-source repositories;
- extracting reusable ideas;
- comparing workflow structures;
- reviewing AI agent systems;
- adapting strong external patterns.

# Inputs

Required inputs:
- repository_url
- user_goal

# Outputs

Expected outputs:
- repository summary;
- reusable patterns;
- risks;
- adaptation opportunities;
- recommended next step.

# Workflow

1. Read the repository README and structure.
2. Identify the project purpose.
3. Identify reusable architecture or workflow patterns.
4. Separate facts from assumptions.
5. Extract patterns that can be adapted.
6. Produce a concise recommendation.

# Constraints

Do not:
- invent repository functionality;
- claim execution without evidence;
- confuse assumptions with facts.

# Failure Modes

Possible failures:
- shallow repository reading;
- overgeneralization;
- copying patterns blindly;
- missing repository constraints.

# Validation Checklist

Before finalizing:
- repository purpose identified;
- reusable patterns extracted;
- assumptions marked;
- risks identified;
- recommendation included.

# References

See `references.md`.

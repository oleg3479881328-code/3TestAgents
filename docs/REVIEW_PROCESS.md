# AI Skill System — Review Process

## Review Purpose

The review process exists to prevent:
- prompt dump degeneration;
- fake execution claims;
- vague workflows;
- low-quality skills;
- vendor lock-in;
- unmaintainable skill growth.

## Review Checklist

Every skill must be checked for:
- clear task boundary;
- defined inputs;
- defined outputs;
- constraints;
- failure modes;
- source attribution;
- compatibility notes;
- validation checklist;
- lifecycle state;
- no fake execution claims.

## Failure Conditions

A skill fails review if:
- the task boundary is unclear;
- inputs or outputs are missing;
- the workflow is too broad;
- references are hidden or missing;
- execution claims cannot be verified;
- the skill duplicates existing active skills.

## Approval Rules

A skill becomes `active` only if:
- review passes;
- lifecycle status is updated;
- references are present;
- workflow is reproducible.

## Reviewer Output Format

Reviewer output should include:
- strengths;
- risks;
- review checklist results;
- approval or rejection;
- required corrections.

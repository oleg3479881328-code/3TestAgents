# AI Skill System — Lifecycle Model

## Lifecycle States

### draft

Raw or newly created skill.

Characteristics:
- incomplete;
- not reviewed;
- not approved for reuse.

### candidate

Structured skill ready for review.

Characteristics:
- metadata exists;
- workflow exists;
- references exist.

### reviewed

Checked by Reviewer Agent or human reviewer.

Characteristics:
- review completed;
- major issues identified.

### active

Approved for reuse.

Characteristics:
- stable enough for operational usage;
- review passed.

### deprecated

Still available but replaced by a better skill.

### retired

Removed from normal usage.

## Transition Rules

Allowed transitions:

```text
draft -> candidate
candidate -> reviewed
reviewed -> active
active -> deprecated
deprecated -> retired
```

## Core Rule

No skill can become active without review.

## State Separation

### Generated State

Proposed by AI but not committed.

### Committed State

Written to GitHub.

### Reviewed State

Checked by reviewer.

### Active State

Approved for operational reuse.

# Review — github-repository-research

## Review Status

Status: reviewed-with-required-improvements

Reviewed artifact:
`skills/research/github-repository-research/SKILL.md`

## Summary

The skill is valid as a first draft and correctly follows the document-first MVP boundary.

It is not ready for `active` status yet.

## Strengths

- Clear task boundary.
- Tool-neutral structure.
- Required inputs are present.
- Expected outputs are present.
- Constraints are present.
- Failure modes are present.
- Validation checklist exists.
- No fake execution claims are present.

## Weaknesses

### Weakness 1 — Output contract is too loose

The skill says what outputs are expected, but does not define a strict output format.

Required improvement:
Add a structured output contract.

### Weakness 2 — Source verification is weak

The workflow says to read README and structure, but does not require source links or evidence markers.

Required improvement:
Require source links or file paths for every major claim.

### Weakness 3 — No scoring model

The skill extracts reusable patterns but does not rank them.

Required improvement:
Add pattern scoring fields:
- usefulness
- portability
- implementation effort
- risk

### Weakness 4 — No explicit adaptation rule

The skill warns against blind copying, but does not define how to adapt patterns.

Required improvement:
Add an adaptation section.

## Review Checklist

- Clear task boundary: pass
- Inputs defined: pass
- Outputs defined: pass
- Constraints defined: pass
- Failure modes defined: pass
- Source attribution: partial
- Validation checklist: pass
- No fake execution claims: pass
- Ready for active status: fail

## Decision

Do not mark this skill as active yet.

Recommended next status:
`candidate`

Reason:
The skill is structured enough to leave `draft`, but not strong enough for `active`.

## Required Next Patch

Update `SKILL.md`:
- change `status` from `draft` to `candidate`;
- change `review_status` from `not_reviewed` to `reviewed_with_required_improvements`;
- add strict output format;
- add evidence rules;
- add pattern scoring model;
- add adaptation rules.

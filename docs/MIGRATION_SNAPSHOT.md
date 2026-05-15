# MIGRATION SNAPSHOT — 3TestAgents / AI Skill System

## Цель

Продолжить проект 3TestAgents как document-first AI Skill Infrastructure без преждевременного runtime/backend/automation.

## Текущее состояние

Репозиторий:
https://github.com/oleg3479881328-code/3TestAgents

Создано:
- workflow-runs/001-first-run-template.md
- workflow-runs/002-ai-skill-system-run.md
- docs/SKILL_SPEC.md
- docs/LIFECYCLE.md
- docs/REVIEW_PROCESS.md
- docs/COMPATIBILITY_MODEL.md
- skills/registry.md
- skills/PROJECT_INDEX.md
- skills/research/github-repository-research/SKILL.md
- skills/research/github-repository-research/references.md
- skills/research/github-repository-research/validation/REVIEW.md
- knowledge-library/README.md
- knowledge-library/PROJECT_INDEX.md
- knowledge-library/patterns/document-first-mvp.md
- knowledge-library/patterns/tool-neutral-core.md
- knowledge-library/patterns/state-separation-in-ai-systems.md
- logs/WORKFLOW_LOG.md

## Подтверждённые решения

1. GitHub = source of truth.
2. Document-first before runtime.
3. Tool-neutral core with adapters later.
4. Skill = folder-based unit with SKILL.md.
5. No skill becomes active without review.
6. First skill candidate: github-repository-research.
7. Current skill status: candidate.
8. Current review_status: reviewed_with_required_improvements.
9. Knowledge Library stores reusable patterns, not executable skills.
10. Registry is mandatory before skill growth.

## Ограничения / запреты

- No backend.
- No frontend.
- No runtime engine.
- No automation layer.
- No vector DB.
- No semantic search.
- No marketplace.
- No mass skill creation.
- No fake execution claims.
- No active skill without review.

## Что НЕ делать

- Не создавать второй skill сейчас.
- Не строить runtime.
- Не уходить в Codex/local execution.
- Не расширять архитектуру ради архитектуры.
- Не превращать repository в prompt dump.

## Следующий шаг — один

Усилить первый skill candidate до состояния approved: обновить github-repository-research/SKILL.md по REVIEW.md, затем повторно провести review и только после этого решить, можно ли перевести skill в active.

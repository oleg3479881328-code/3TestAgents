# MIGRATION SNAPSHOT — 3TestAgents / AI Skill System

## Цель

Продолжить проект 3TestAgents как document-first AI Skill Infrastructure без преждевременного runtime/backend/automation.

Система должна оставаться:
- repository-first;
- governance-driven;
- tool-neutral;
- review-based;
- knowledge-preserving.

## Текущее состояние

Репозиторий:
https://github.com/oleg3479881328-code/3TestAgents

### Workflow Layer

Создано:
- `workflow-runs/001-first-run-template.md`
- `workflow-runs/002-ai-skill-system-run.md`

Workflow Run 002:
- восстановлен как полноценный compact full record;
- больше не содержит `[unchanged]` placeholders;
- содержит все workflow stages:
  - Pre-Architect
  - Research Agent
  - Architect
  - Coder-Spec
  - Reviewer
  - Librarian

### Specification Layer

Создано:
- `docs/SKILL_SPEC.md`
- `docs/LIFECYCLE.md`
- `docs/REVIEW_PROCESS.md`
- `docs/COMPATIBILITY_MODEL.md`

### Skill Layer

Создано:
- `skills/research/github-repository-research/SKILL.md`
- `skills/research/github-repository-research/references.md`
- `skills/research/github-repository-research/validation/REVIEW.md`

Текущее состояние первого skill:
- status: `candidate`
- review_status:
  `reviewed_with_required_improvements`
- version:
  `0.1.1`

Skill усилен:
- evidence rules;
- pattern scoring model;
- adaptation rules;
- strict output format;
- stronger validation.

### Governance Layer

Создано:
- `skills/registry.md`
- `skills/PROJECT_INDEX.md`

Registry tracking включает:
- lifecycle state;
- review state;
- compatibility;
- versioning;
- governance rules.

### Knowledge Layer

Создано:
- `knowledge-library/README.md`
- `knowledge-library/PROJECT_INDEX.md`
- `knowledge-library/patterns/document-first-mvp.md`
- `knowledge-library/patterns/tool-neutral-core.md`
- `knowledge-library/patterns/state-separation-in-ai-systems.md`

### Logging Layer

Создано:
- `logs/WORKFLOW_LOG.md`

Log фиксирует:
- workflow execution history;
- architectural decisions;
- governance decisions;
- resulting repository states;
- risks;
- lessons learned.

## Подтверждённые решения

1. GitHub = source of truth.
2. Document-first before runtime.
3. Tool-neutral core with adapters later.
4. Skill = folder-based unit with SKILL.md.
5. No skill becomes active without review.
6. Registry mandatory before scale.
7. Knowledge Library separate from executable skills.
8. Generated vs committed vs reviewed vs active state separation.
9. Governance before growth.
10. Atomic skills first.
11. Reuse-first open-source research workflow.
12. Repository artifacts are canonical executed state.

## Ограничения / запреты

Still forbidden:
- backend;
- frontend;
- runtime engine;
- orchestration layer;
- automation layer;
- vector DB;
- semantic search;
- marketplace;
- mass skill creation;
- fake execution claims.

## Что НЕ делать

- Не строить runtime сейчас.
- Не подключать automation.
- Не уходить в Codex execution layer.
- Не плодить десятки skills.
- Не расширять архитектуру ради архитектуры.
- Не превращать repository в prompt dump.
- Не обходить review process.

## Главные риски

1. Prompt dump degeneration.
2. Premature runtime expansion.
3. Vendor lock-in.
4. Governance collapse during scaling.
5. Fake execution claims.
6. Overengineering before validation.

## Текущая фаза проекта

Phase:
Document-first AI Skill Infrastructure.

Subphase:
Governance stabilization and first skill validation.

## Следующий шаг — один

Провести второй review cycle для:
`skills/research/github-repository-research/SKILL.md`

Цель:
решить, можно ли перевести первый skill из `candidate` в `active`.

Никакие новые skills не создавать до завершения этого review cycle.

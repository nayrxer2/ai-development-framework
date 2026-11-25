# Skills Library

**Document:** `skills/README.md`  
**Status:** Draft  
**Version:** 0.1.0

---

## 1. Purpose

The Skills Library contains reusable expertise, procedures, decision criteria, and validation methods used by agents across the AI Development Framework.

Skills provide the practical knowledge required to perform specific types of work.

This directory is designed to be:

- Reusable across agents and projects.
- Independent of specific AI platforms.
- Modular and progressively loadable.
- Consistent in structure and quality.
- Expandable without unnecessary duplication.

This document serves as the navigation guide for the library.

For the complete skill-system specification, see `SKILL_ARCHITECTURE.md`.

## 2. Directory Structure

```text
skills/
├── README.md
├── SKILL_ARCHITECTURE.md
│
├── architecture/
│   └── SKILL.md
│
├── product-management/
│   └── SKILL.md
│
├── ui-ux/
│   └── SKILL.md
│
├── frontend/
│   └── SKILL.md
│
├── backend/
│   └── SKILL.md
│
├── database/
│   └── SKILL.md
│
├── testing/
│   └── SKILL.md
│
├── security/
│   └── SKILL.md
│
├── devops/
│   └── SKILL.md
│
├── code-quality/
│   └── SKILL.md
│
└── marketing/
    └── SKILL.md
```

This represents the initial domain organization, not a requirement to create every skill immediately.

Specialized skills and supporting references MAY be added within appropriate domains when justified.

## 3. Skill Categories

| Domain | Primary Responsibility |
|---|---|
| Architecture | System design, technical decisions, architecture reviews, and project structure. |
| Product Management | Product discovery, requirements, prioritization, and roadmaps. |
| UI/UX | User research, user journeys, interface design, usability, and design systems. |
| Frontend | Client-side implementation, components, routing, state, styling, and performance. |
| Backend | Server-side logic, APIs, integrations, and business logic. |
| Database | Data modeling, schema design, migrations, and database optimization. |
| Testing | Test strategy, test implementation, automation, and quality assurance. |
| Security | Threat analysis, secure development, vulnerability assessment, and security controls. |
| DevOps | Infrastructure, CI/CD, deployment, monitoring, and operational reliability. |
| Code Quality | Maintainability, refactoring, code standards, and technical debt reduction. |
| Marketing | Positioning, market research, go-to-market strategy, content, and promotion. |

Domain boundaries MUST remain clear.

Related domains MAY collaborate, but one skill MUST NOT silently assume responsibilities belonging to another domain.

## 4. How to Navigate the Library

Use the following navigation process:

1. Identify the task and expected outcome.
2. Determine the primary domain.
3. Open the relevant domain's `SKILL.md`.
4. Identify applicable specialized skills.
5. Load only the required specialized skills.
6. Consult supporting references when necessary.
7. Follow the skill's procedure and validation criteria.

Do not load the entire library for every task.

## 5. Skill File Conventions

Individual skills MUST follow the framework's naming conventions.

| File or Directory | Purpose |
|---|---|
| `SKILL.md` | Main skill definition or domain entry point. |
| `SKILL_ARCHITECTURE.md` | Defines the architecture of the entire skill system. |
| `README.md` | Provides navigation and general guidance. |
| Descriptive `.md` files | Supporting references or supplementary documentation. |

Individual skills MUST follow:

`templates/SKILL.template.md`

The authoritative skill-system specification is:

`skills/SKILL_ARCHITECTURE.md`

## 6. Domain Entry Points

Each domain-level `SKILL.md` SHOULD:

- Define the domain's purpose.
- Identify its responsibilities and exclusions.
- Describe its activation conditions.
- Provide guidance for selecting specialized skills.
- Identify relevant dependencies.
- Explain validation expectations.
- Link to relevant references.

A domain entry point is not automatically a complete implementation manual.

Its purpose is to guide discovery and provide sufficient domain context.

## 7. Specialized Skills

Specialized skills SHOULD be created when a capability has enough independent value to justify separate documentation and loading.

Examples:

**Architecture**
- System design.
- Project structure.
- Technical decisions.
- Architecture review.

**Frontend**
- Reusable components.
- Page composition.
- State management.
- Styling and responsive design.
- Forms and validation.
- Performance optimization.

These are examples, not mandatory folders.

Avoid creating specialized skills simply to categorize every technical topic.

## 8. Skill Usage Across Agents

Skills are shared capabilities.

Agents select skills according to their responsibilities and assigned tasks.

Examples:

| Agent | Possible Skills |
|---|---|
| Software Architect/Orchestrator | Architecture, product management, security, project structure. |
| Software Developer | Frontend, backend, database, testing, code quality. |
| Independent Reviewer | Architecture review, testing, security, code quality. |

This table is illustrative. Actual skill selection MUST depend on task requirements.

An agent's definition establishes its authority and accountability. A skill provides the expertise used to perform the work.

## 9. Skill Creation and Maintenance

Before creating a new skill:

1. Search for an existing skill that already covers the capability.
2. Determine whether the content belongs in an existing skill.
3. Define its purpose, scope, and activation triggers.
4. Identify dependencies and potential duplication.
5. Use `templates/SKILL.template.md`.
6. Define validation and evaluation scenarios.
7. Test the skill before considering it validated.

Skill changes MUST follow the framework's change-control requirements.

## 10. Skill Maturity

Skills SHOULD progress through these lifecycle states:

- PROPOSED
- DRAFT
- SPECIFIED
- PILOTING
- VALIDATED
- DEPRECATED
- RETIRED

A documented skill is not necessarily a tested or validated skill.

Its maturity status MUST reflect actual evidence.

## 11. Important Operating Rules

1. Load only skills relevant to the assigned task.
2. Prefer existing skills over unnecessary duplication.
3. Follow the skill's defined scope and exclusions.
4. Do not treat skill instructions as execution permissions.
5. Follow applicable governance and approval requirements.
6. Disclose missing expertise and runtime limitations.
7. Validate outputs against defined acceptance criteria.
8. Improve skills using evidence from actual task execution.

## 12. Current Implementation Status

The directory structure defines the intended organization of the skill library.

It does not establish that every domain or specialized skill has been implemented.

Likewise, documenting progressive disclosure does not mean the current runtime automatically supports it.

Actual discovery, loading, and evaluation capabilities MUST be verified through the relevant runtime adapter.

The initial implementation SHOULD focus on one complete, tested skill before expanding the library.

---

**End of Document**
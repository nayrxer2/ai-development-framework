# AI Development Framework

A platform-independent framework for organizing AI-assisted software development through explicit roles, reusable skills, governance, and operational workflows.

## Structure

- [`core/`](core/FRAMEWORK_MODEL.md) — model, terminology, principles, and architecture.
- [`organization/`](organization/AGENT_CATALOG.md) — agent catalog, departments, agent definitions, and responsibility matrix.
- [`skills/`](skills/README.md) — reusable domain capabilities.
- [`governance/`](governance/GLOBAL_RULES.md) — global rules, boundaries, change control, security, and approvals.
- [`operations/`](operations/workflows/TASK_LIFECYCLE.md) — workflows, delegation, and handoffs.
- [`templates/`](templates/AGENT.template.md) — reusable agent, skill, task, handoff, and decision templates.
- [`references/`](references/) — supporting reference material.
- [`adapters/`](adapters/README.md) — platform-specific integrations.
- [`evaluations/`](evaluations/README.md) — test cases and evaluation reports.
- [`projects/`](projects/README.md) — project-specific adoption and context.

## Getting started

Read the [framework model](core/FRAMEWORK_MODEL.md), [principles](core/PRINCIPLES.md), and [global rules](governance/GLOBAL_RULES.md). Select an accountable role from the [agent catalog](organization/AGENT_CATALOG.md), load only relevant skills, and use the task lifecycle and handoff contract to coordinate work.

Use the templates when adding framework content. Keep shared policy in governance, platform-specific behavior in adapters, and project-specific requirements in project context.

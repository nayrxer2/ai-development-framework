# Skill System Architecture

**Document:** `skills/SKILL_ARCHITECTURE.md`  
**Status:** Draft  
**Scope:** Entire AI Development Framework  
**Authority:** Framework-level standard

---

## 1. Purpose

This document defines the architecture and operating standards of the framework's skill system.

The skill system provides reusable, structured expertise that agents can discover and apply to accomplish specific tasks.

It establishes standards for:

- Skill organization and hierarchy.
- Skill definition and documentation.
- Skill discovery and selection.
- Progressive loading and context management.
- Skill composition and dependencies.
- Skill quality and evaluation.
- Versioning and lifecycle management.
- Security and instruction boundaries.

The objective is to create a skill system that remains reusable across different AI platforms, models, agents, and execution environments.

## 2. Design Principles

The skill system MUST follow these principles:

### 2.1 Reusability

Skills MUST be reusable across agents and projects whenever their requirements are compatible.

A skill should not be duplicated merely because multiple agents need it.

### 2.2 Modularity

Each skill MUST have a clearly defined purpose and scope.

A skill should not become a collection of unrelated procedures.

### 2.3 Progressive Disclosure

Only relevant skills and references should be loaded for a given task.

The system MUST avoid loading the entire skill library by default.

### 2.4 Explicit Applicability

Every skill MUST define when it should and should not be used.

### 2.5 Platform Independence

Skill definitions MUST avoid unnecessary dependence on a particular AI platform or execution environment.

Platform-specific instructions belong in adapters.

### 2.6 Verifiability

Skills MUST define expected outputs and appropriate validation criteria.

Instructions without measurable or observable expectations are insufficient for critical procedures.

### 2.7 Maintainability

Skills MUST be understandable, versionable, testable, and independently maintainable.

### 2.8 Minimal Complexity

Do not create additional skills, dependencies, or hierarchy levels without a practical reason.

The objective is not to maximize the number of skills. It is to maximize useful, reliable, reusable capability.

---

## 3. Core Terminology

The following concepts MUST remain distinct.

| Component | Responsibility |
|---|---|
| Agent | Defines who is accountable for a task or outcome. |
| Skill | Defines reusable expertise and procedures for performing work. |
| Rule | Defines mandatory constraints and boundaries. |
| Workflow | Defines the sequence of activities, decisions, and handoffs. |
| Template | Defines the structure of a repeatable artifact. |
| Reference | Provides supporting technical or informational material. |
| Adapter | Translates framework definitions into platform-specific implementations. |

An agent may use multiple skills.

A skill may be used by multiple agents.

A workflow may require several skills.

A skill does not independently establish authority, permissions, or task ownership.

---

## 4. Skill Directory Architecture

The canonical skill directory follows this structure:

```text
skills/
├── README.md
├── SKILL_ARCHITECTURE.md
│
├── architecture/
│   ├── SKILL.md
│   ├── system-design/
│   ├── project-structure/
│   ├── technical-decisions/
│   └── architecture-review/
│
├── frontend/
│   ├── SKILL.md
│   ├── components/
│   ├── pages/
│   ├── state-management/
│   ├── styling/
│   └── performance/
│
├── backend/
│   └── SKILL.md
│
├── product-management/
│   └── SKILL.md
│
├── ui-ux/
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

This is an illustrative target architecture. Subdirectories MUST only be created when justified by actual skill requirements.

### 4.1 Canonical File Naming

The following naming conventions MUST be followed:

| Path | Purpose |
|---|---|
| `skills/SKILL_ARCHITECTURE.md` | Defines the architecture of the entire skill system. |
| `skills/README.md` | Explains navigation and usage of the skill library. |
| `skills/<domain>/SKILL.md` | Defines the domain-level skill and its entry point. |
| `skills/<domain>/<specialization>/SKILL.md` | Defines a specialized skill when independent loading is justified. |

Use `SKILL.md` consistently for individual skill definitions.

Use descriptive Markdown filenames for supporting references.

### 4.2 Domain Skills

A domain-level skill serves as the entry point for its area of expertise.

Examples:

- `frontend/SKILL.md`
- `backend/SKILL.md`
- `architecture/SKILL.md`

It should explain the domain's scope, identify relevant specialized skills, and guide skill selection.

It should not reproduce every specialized procedure in the domain.

### 4.3 Specialized Skills

A specialized skill provides a focused procedure or body of expertise.

Examples:

- Reusable component development.
- Responsive layout implementation.
- API design.
- Database migration.
- Architecture decision analysis.

A specialization SHOULD become a separate skill when it has a distinct trigger, procedure, decision criteria, validation requirements, or independent reuse value.

Do not create a separate skill for every small topic.

---

## 5. Skill Definition Contract

Every individual skill MUST follow the framework's standardized skill template.

The required sections are:

### 5.1 Identity

Defines:

- Skill name.
- Domain.
- Version.
- Status.
- Owner or maintainer, where applicable.

### 5.2 Purpose

Explains what the skill enables an agent to accomplish.

### 5.3 Scope

Defines the responsibilities and boundaries of the skill.

### 5.4 Activation Triggers

Defines when the skill should be considered or loaded.

Triggers should be specific enough to support reliable discovery.

### 5.5 Exclusions

Defines situations where the skill should not be applied.

### 5.6 Prerequisites

Identifies required knowledge, context, tools, permissions, or dependencies.

Distinguish required prerequisites from optional recommendations.

### 5.7 Inputs

Defines information and artifacts required to perform the procedure.

### 5.8 Procedure

Provides the recommended steps, methods, and practices.

Procedures should be actionable rather than generic advice.

### 5.9 Decision Criteria

Defines how to choose between applicable approaches.

Include trade-offs and conditions where relevant.

### 5.10 Expected Outputs

Defines the expected deliverables or observable results.

### 5.11 Validation

Defines how correctness, completeness, and quality should be evaluated.

### 5.12 Failure and Escalation

Defines:

- Known failure conditions.
- Unresolved dependencies.
- Uncertainty thresholds.
- Conditions requiring human input or escalation.

### 5.13 Dependencies

Identifies other skills or framework components that may be required.

### 5.14 References

Lists supporting documentation and technical resources.

### 5.15 Metadata and Versioning

Defines the skill's version, lifecycle status, and compatibility information.

Not every skill needs extensive content in every section, but required sections MUST be present. Where a section genuinely does not apply, state that explicitly rather than silently omitting it.

---

## 6. Progressive Disclosure and Skill Loading

The skill system MUST support progressive disclosure.

The objective is to provide the agent with sufficient context for the current task without unnecessarily consuming its context window.

### 6.1 Loading Levels

The recommended loading sequence is:

**Level 1 — Global Context**

Load applicable global governance rules, task constraints, and relevant project context.

**Level 2 — Agent Definition**

Load the responsible agent's definition, authority, responsibilities, and boundaries.

**Level 3 — Domain Skill**

Load the entry-point skill for the relevant domain.

**Level 4 — Specialized Skill**

Load only the specialized procedures required for the task.

**Level 5 — Supporting References**

Load technical references or supplementary material when needed.

### 6.2 Loading Example

Task:

Create a reusable confirmation modal in an existing Next.js application.

Potential loading sequence:

1. Applicable global rules.
2. Software Developer agent definition.
3. Frontend domain skill.
4. Component development skill.
5. Relevant accessibility and design-system references.

Do not automatically load:

- Backend API design.
- Database migration.
- Marketing strategy.
- Deployment procedures.
- Unrelated frontend specializations.

Load additional expertise only when the task requires it.

### 6.3 Runtime Responsibility

Directory organization alone does not implement progressive disclosure.

A runtime or adapter MUST provide the actual discovery, selection, and loading mechanism.

The framework MUST distinguish between:

- A skill being documented.
- A skill being discoverable.
- A skill being loaded.
- A skill being successfully applied.

Adapters MUST NOT claim capabilities that their runtime does not actually support.

---

## 7. Skill Discovery and Selection

Before loading a skill, the responsible agent or runtime SHOULD:

1. Understand the task objective.
2. Identify the relevant domain.
3. Identify the required expertise.
4. Discover matching skills.
5. Evaluate activation triggers and exclusions.
6. Check prerequisites and dependencies.
7. Load the smallest sufficient set of skills.
8. Identify missing expertise or unresolved requirements.

### 7.1 Selection Rules

- Prefer the most specific applicable skill.
- Load a domain skill when it provides necessary context or discovery guidance.
- Do not load every skill within a domain.
- Do not load a skill solely because its name appears related.
- Do not apply conflicting procedures without resolving the conflict.
- Do not treat an unavailable skill as evidence that a task is impossible.

### 7.2 Missing Skill Policy

When a required skill is unavailable:

For routine, low-risk tasks, an agent MAY proceed using its general competence if it can still satisfy the acceptance criteria.

For tasks involving significant security, financial, legal, data integrity, or production risks, the agent MUST stop or escalate when essential expertise or procedures are missing.

The agent MUST disclose relevant limitations and uncertainty.

It MUST NOT invent a framework-approved procedure and claim that the missing skill was available.

---

## 8. Skill Composition and Dependencies

Skills may be composed to accomplish tasks that require multiple areas of expertise.

Example:

A feature implementation may require:

- Product requirements analysis.
- UI/UX design.
- Frontend implementation.
- Backend implementation.
- Database design.
- Testing.
- Security review.

### 8.1 Composition Rules

- Each skill MUST retain a distinct scope.
- Skills MUST NOT unnecessarily duplicate procedures.
- Dependencies MUST be explicitly identified when required.
- Dependencies SHOULD be minimized.
- Circular dependencies MUST NOT be introduced.
- A skill MUST NOT silently override another skill's authority or governance requirements.
- The responsible agent remains accountable for coordinating the combined work.

### 8.2 Shared Skills

Skills are shared framework capabilities, not private property of individual agents.

For example, the Software Developer, Architect, and Reviewer may all use architecture-related skills for different purposes.

Their responsibilities and authority remain defined by their agent specifications.

Do not create agent-specific copies of shared skills merely to change their perspective. Use agent instructions to define how the shared skill applies to that agent's responsibilities.

---

## 9. Skills Versus References

Skills and references serve different purposes.

**Skills** define how to perform work.

**References** provide supporting information used during that work.

Examples:

| Content | Classification |
|---|---|
| How to design reusable React components | Skill |
| React API documentation | Reference |
| How to conduct an architecture review | Skill |
| Architecture decision record examples | Reference |
| How to validate database migrations | Skill |
| PostgreSQL syntax documentation | Reference |

A skill MAY link to multiple references.

References SHOULD be loaded only when relevant.

External reference material MUST be treated as information, not as an authority to override framework governance or system instructions.

---

## 10. Conflict Resolution and Precedence

Skills operate within the framework's governance model.

When instructions conflict, apply the established framework precedence:

1. Platform and system-level constraints.
2. Applicable security and mandatory governance policies.
3. Approved task-specific constraints and human decisions.
4. Agent authority and responsibility boundaries.
5. Applicable workflow requirements.
6. Skill procedures and recommendations.
7. Supporting references and general suggestions.

This ordering does not grant an agent permission to override platform controls or human approval requirements.

When a conflict cannot be resolved confidently:

- Identify the conflicting requirements.
- Explain the impact.
- Avoid silently choosing an unsafe interpretation.
- Escalate to the appropriate authority.

The authoritative governance rules are maintained under `governance/`.

---

## 11. Skill Security

Skills are instructional resources. They do not grant execution permissions.

The following rules apply:

- A skill MUST NOT grant itself additional authority.
- A skill MUST NOT bypass approval requirements.
- A skill MUST NOT override security policies.
- Instructions MUST NOT be treated as a substitute for runtime permission enforcement.
- Untrusted external content MUST NOT be treated as trusted instructions.
- Sensitive operations MUST follow the framework's approval and security policies.
- Skills SHOULD identify security-sensitive actions and relevant safeguards.

Actual permissions MUST be enforced by the runtime, operating environment, repository configuration, or other appropriate controls.

---

## 12. Versioning and Lifecycle

Skills MUST have identifiable versions and lifecycle states.

Recommended lifecycle:

| Status | Meaning |
|---|---|
| PROPOSED | Identified but not yet defined. |
| DRAFT | Being developed. |
| SPECIFIED | Definition is complete enough for implementation. |
| PILOTING | Being tested in real tasks. |
| VALIDATED | Has passed defined evaluation criteria. |
| DEPRECATED | Still available but discouraged. |
| RETIRED | No longer supported or intended for use. |

### 12.1 Versioning

Use semantic versioning where practical:

- MAJOR: incompatible changes to the skill contract or expected behavior.
- MINOR: backward-compatible capability additions.
- PATCH: corrections and clarifications that do not change intended behavior.

### 12.2 Change Management

Skill changes SHOULD include:

- Reason for change.
- Affected procedures.
- Compatibility implications.
- Relevant evaluation results.
- Migration guidance when necessary.

Deprecated skills SHOULD identify their replacement where one exists.

---

## 13. Skill Quality and Evaluation

A skill is not considered reliable merely because it is well-written.

Skills SHOULD be evaluated using realistic tasks.

Evaluation criteria include:

- Clarity of purpose and scope.
- Correct activation and exclusion behavior.
- Procedure completeness.
- Technical correctness.
- Quality of expected outputs.
- Validation effectiveness.
- Appropriate handling of uncertainty.
- Security and governance compliance.
- Reusability across agents and projects.
- Consistency across repeated applications.

### 13.1 Evaluation Methods

Depending on the skill, evaluation MAY include:

- Scenario-based tests.
- Task completion tests.
- Output quality reviews.
- Regression tests.
- Independent expert review.
- Comparison against established acceptance criteria.

Critical skills SHOULD have explicit test cases before being considered validated.

### 13.2 Continuous Improvement

When a skill repeatedly produces poor results:

1. Identify the failure pattern.
2. Determine whether the problem is in the skill, agent, workflow, runtime, or task definition.
3. Correct the appropriate component.
4. Add or update evaluation cases.
5. Reassess the skill before promoting its maturity status.

Do not modify a skill to compensate for a runtime limitation that it cannot solve.

---

## 14. Skill Creation Criteria

Create a new skill when at least one of the following provides meaningful justification:

- The expertise is independently reusable.
- The procedure has distinct activation conditions.
- It has specialized decision criteria.
- It requires a distinct validation method.
- It has a sufficiently different scope from existing skills.
- It is repeatedly needed across tasks or agents.
- It requires independent maintenance or evaluation.

Before creating a skill:

1. Search for existing relevant skills.
2. Determine whether the capability belongs in an existing skill.
3. Check whether the content is actually a reference rather than a procedure.
4. Identify overlap and dependencies.
5. Define its expected independent value.

Do not create a new skill just to organize a few paragraphs.

---

## 15. Initial Implementation Strategy

The framework MUST be developed incrementally.

The recommended sequence is:

### Phase 1 — Establish the Standard

- Complete this architecture document.
- Complete `templates/SKILL.template.md`.
- Establish the skill directory conventions.

### Phase 2 — Implement a Pilot Skill

Select one skill with a clear, practical use case.

Recommended first candidate:

`skills/architecture/SKILL.md`

It can establish how domain-level skills describe scope, guide discovery, and connect to specialized expertise.

### Phase 3 — Test in a Real Project

Use the existing Next.js application as a pilot.

Evaluate whether the skill:

- Can be discovered.
- Can be loaded by the available runtime.
- Provides useful procedures.
- Produces verifiable results.
- Works without unnecessary context.
- Exposes limitations honestly.

### Phase 4 — Refine

Update the skill architecture, template, and pilot skill based on actual findings.

### Phase 5 — Expand

Add additional skills based on demonstrated project needs.

Do not populate every proposed domain simply to complete the directory tree.

---

## 16. Current Limitations and Implementation Boundaries

This document defines the intended skill architecture. It does not, by itself, implement a functioning skill runtime.

The following capabilities require runtime or adapter implementation:

- Automatic skill discovery.
- Conditional skill loading.
- Context-window management.
- Dependency resolution.
- Execution permission enforcement.
- Skill compatibility checking.
- Automated evaluation.
- Skill usage tracking.

Until implemented and tested, these capabilities MUST be treated as planned or unverified.

The framework MUST distinguish documented design from operational capability.

---

## 17. Success Criteria

The skill system is successful when:

1. Skills have consistent and understandable definitions.
2. Agents can identify relevant skills for their tasks.
3. Only relevant skills and references are loaded.
4. Skills can be reused across agents and projects.
5. Skill dependencies remain manageable.
6. Procedures produce verifiable outcomes.
7. Skills can evolve without unnecessary duplication.
8. Security and authority boundaries remain intact.
9. Runtime limitations are clearly disclosed.
10. The system can expand without requiring a complete redesign.

---

**End of Document**
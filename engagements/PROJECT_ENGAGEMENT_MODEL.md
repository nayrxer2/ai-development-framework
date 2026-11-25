# Project Engagement Model

**Version:** 0.1.0  
**Status:** DRAFT  
**Document Type:** Operational Model  
**Owner:** AI Development Agency

---

## 1. Purpose

This document defines how the AI Development Agency establishes, operates, manages, and closes engagements with independently owned software projects.

An engagement represents a formal, bounded working relationship between the agency and a client project.

It establishes the context, responsibilities, scope, permissions, capabilities, deliverables, and operational boundaries required for the agency to perform work reliably.

The model must support both:

- New projects that have not yet entered development.
- Existing projects with established repositories, architecture, and development history.

The engagement process must be repeatable across different projects, clients, technologies, and execution platforms.

## 2. Core Principles

Every engagement must follow these principles:

1. **Project independence:** The client project retains its own repository, ownership, architecture, and conventions.
2. **Explicit authorization:** The agency operates only within granted authority.
3. **Context before execution:** The agency must understand the project before making changes.
4. **Least privilege:** Access must be limited to what the engagement requires.
5. **Relevant specialization:** Only necessary agents, skills, and workflows should be activated.
6. **Clear accountability:** Every task has one accountable owner.
7. **Evidence-based delivery:** Completion requires appropriate verification evidence.
8. **Engagement isolation:** Project information and permissions must not leak between engagements.
9. **Controlled changes:** Scope, requirements, and authority changes must be documented.
10. **Capability transparency:** The agency must disclose limitations in its execution environment.

## 3. Engagement Definition

An engagement is a structured operational record containing the information required to manage the agency's relationship with one project.

Each engagement must have:

- A unique engagement identifier.
- A project identity.
- A project owner or authorized representative.
- An engagement objective.
- An agreed scope.
- Project context.
- Applicable agents and skills.
- Access and permission boundaries.
- Execution constraints.
- Deliverables and acceptance criteria.
- Approval requirements.
- Work history and evidence.
- Current engagement status.

An engagement does not require a separate Git repository.

The engagement record may be maintained in the agency workspace, a designated project-specific directory, or a compatible external system.

The chosen storage mechanism must preserve project isolation and access boundaries.

## 4. Engagement Types

### 4.1 New Project Engagement

Used when a project is being planned or created.

Typical activities:

- Product discovery.
- Business objective clarification.
- User and stakeholder identification.
- Requirements gathering.
- Product scope definition.
- Technical feasibility assessment.
- Architecture planning.
- Technology evaluation.
- Initial development roadmap.

The agency must not assume that a proposed technology stack or architecture has already been approved.

### 4.2 Existing Project Engagement

Used when the agency is joining an existing software project.

Typical activities:

- Repository inspection.
- Technology stack identification.
- Architecture assessment.
- Existing functionality analysis.
- Code quality assessment.
- Testing and deployment review.
- Technical debt identification.
- Security and operational risk assessment.
- Development workflow discovery.

The agency must inspect the existing project before proposing structural changes.

### 4.3 Maintenance and Improvement Engagement

Used when the project already exists and the objective is ongoing maintenance, feature development, optimization, or technical improvement.

Typical activities:

- Bug investigation.
- Feature implementation.
- Refactoring.
- Performance improvement.
- Dependency maintenance.
- Security remediation.
- Documentation improvement.
- Test coverage improvement.

The agency must distinguish maintenance work from scope-expanding development.

## 5. Engagement Lifecycle

Every engagement follows a controlled lifecycle.

### Stage 1 — Initiation

**Objective:** Establish the purpose of the engagement.

The agency collects:

- Project name.
- Project type.
- Project owner.
- Repository or project location.
- Primary objective.
- Initial expectations.
- Known constraints.

The agency assigns a unique engagement identifier.

No implementation is authorized merely because an engagement has been initiated.

**Output:** Engagement initiation record.

### Stage 2 — Framework Preparation

**Objective:** Prepare the agency to work on the project.

The orchestrator:

1. Identifies the applicable framework version.
2. Loads available organizational instructions.
3. Identifies relevant agent definitions.
4. Identifies potentially relevant skills.
5. Reviews applicable governance policies.
6. Checks available runtime capabilities.
7. Identifies missing or inaccessible instructions.

The orchestrator must not claim that an agent, skill, policy, or capability is active if it has not actually been made available.

**Output:** Framework readiness assessment.

### Stage 3 — Project Discovery

**Objective:** Understand the project and its current state.

For existing projects, inspect:

- Repository structure.
- Technology stack.
- Application entry points.
- Existing architecture.
- Dependencies.
- Configuration.
- Existing documentation.
- Tests and development scripts.
- Build and deployment processes.
- Relevant security boundaries.

For new projects, investigate:

- Business objectives.
- Intended users.
- Core problems.
- Product requirements.
- Functional requirements.
- Non-functional requirements.
- Constraints.
- Dependencies.
- Initial feasibility.

The agency must distinguish verified information from assumptions.

Discovery must be read-only unless additional authorization is explicitly granted.

**Output:** Project discovery report.

### Stage 4 — Assessment

**Objective:** Determine the project's needs and readiness.

The agency evaluates:

- Current project maturity.
- Requirement completeness.
- Technical risks.
- Business risks.
- Architectural concerns.
- Existing limitations.
- Missing information.
- Dependencies.
- Required expertise.
- Execution feasibility.

For existing projects, findings must be grounded in repository evidence.

For new projects, recommendations must identify assumptions and unresolved requirements.

**Output:** Engagement assessment.

### Stage 5 — Engagement Planning

**Objective:** Define how the agency will perform the work.

The orchestrator prepares:

- Engagement objectives.
- Scope and exclusions.
- Deliverables.
- Work phases.
- Task breakdown.
- Accountable agents.
- Required contributors.
- Activated skills.
- Dependencies.
- Acceptance criteria.
- Verification requirements.
- Risks and mitigations.
- Approval checkpoints.
- Execution constraints.

Only relevant agents and skills should be selected.

Available skills are not automatically activated skills.

**Output:** Engagement execution plan.

### Stage 6 — Client Approval

**Objective:** Obtain authorization before execution.

The project owner reviews:

- Project understanding.
- Objectives.
- Scope.
- Proposed approach.
- Deliverables.
- Risks.
- Required permissions.
- Approval-required actions.
- Timeline or milestones, where applicable.

The project owner may:

- Approve the plan.
- Reject the plan.
- Request changes.
- Approve only selected phases.
- Provide additional information.

Approval must be explicit and traceable.

Approval of a general plan does not automatically authorize every future high-risk action.

**Output:** Approved engagement plan or documented rejection.

### Stage 7 — Execution

**Objective:** Perform authorized work.

The agency:

1. Creates and assigns tasks.
2. Confirms task authorization.
3. Activates required agents and skills.
4. Checks dependencies.
5. Performs the assigned work.
6. Records decisions and changes.
7. Produces required artifacts.
8. Escalates blockers and approval requirements.

Tasks must follow the framework's task lifecycle and handoff contracts.

The agency must stop or seek authorization when a task exceeds its granted scope or authority.

**Output:** Completed work artifacts and task records.

### Stage 8 — Verification

**Objective:** Establish whether the delivered work meets its acceptance criteria.

Verification may include:

- Automated tests.
- Type checking.
- Build validation.
- Static analysis.
- Security checks.
- Manual testing.
- Regression testing.
- Code review.
- Independent review.

Verification depth must be proportional to risk.

High-risk changes require appropriate independent verification.

The agency must report tests that were not run, failed checks, environmental limitations, and unresolved issues.

**Output:** Verification report.

### Stage 9 — Delivery and Acceptance

**Objective:** Present completed work to the project owner.

The delivery report must include:

- Original objective.
- Completed scope.
- Changed artifacts.
- Important implementation decisions.
- Verification performed.
- Verification results.
- Known limitations.
- Outstanding work.
- Remaining risks.
- Required client actions.

The project owner determines whether deliverables are accepted where client acceptance is required.

The agency must not mark rejected or unverified work as accepted.

**Output:** Delivery report and acceptance record.

### Stage 10 — Closure or Continuation

**Objective:** Close or continue the engagement in a controlled manner.

Before closure:

- Confirm task statuses.
- Record outstanding issues.
- Preserve relevant decisions.
- Record final verification evidence.
- Document unresolved risks.
- Confirm access and permission handling.
- Record final engagement status.

An engagement may be:

- Closed.
- Suspended.
- Cancelled.
- Continued under an updated scope.

Closing an engagement does not mean deleting the client's project or its history.

**Output:** Engagement closure record.

## 6. Engagement Status Model

The engagement uses the following statuses:

| Status | Meaning |
|---|---|
| `INITIATED` | Engagement has been requested. |
| `PREPARING` | Framework and runtime preparation is underway. |
| `DISCOVERING` | Project discovery is underway. |
| `ASSESSING` | Project assessment is underway. |
| `PLANNING` | Execution plan is being prepared. |
| `AWAITING_APPROVAL` | Client approval is required. |
| `APPROVED` | The applicable plan has been authorized. |
| `ACTIVE` | Authorized work is in progress. |
| `BLOCKED` | Progress is prevented by a dependency, missing information, or approval. |
| `VERIFYING` | Completed work is being verified. |
| `AWAITING_ACCEPTANCE` | Deliverables are awaiting client acceptance. |
| `COMPLETED` | Engagement objectives and closure requirements have been satisfied. |
| `SUSPENDED` | Engagement is temporarily paused. |
| `CANCELLED` | Engagement has been terminated without normal completion. |

Status transitions must be controlled and recorded.

An engagement must not transition to `COMPLETED` while required deliverables, verification, or closure obligations remain unresolved.

## 7. Engagement Scope and Change Control

Every engagement must define:

### Included Scope

The work the agency is authorized to perform.

### Excluded Scope

Work explicitly outside the engagement.

### Conditional Scope

Work that may be performed only after additional approval.

Scope changes must be documented.

The agency must not silently expand project objectives, introduce unrelated features, or perform additional work simply because it identifies an opportunity.

Changes affecting budget, schedule, architecture, security, production behavior, or contractual commitments require the appropriate approval.

Refer to the framework's change-control and execution-authority policies.

## 8. Agent and Skill Selection

The orchestrator is responsible for selecting appropriate organizational capabilities.

Selection must be based on:

- Task requirements.
- Technical complexity.
- Risk.
- Required expertise.
- Dependencies.
- Available runtime capabilities.

### Initial Agency Roles

The initial organizational structure should use:

1. Software Architect / Orchestrator.
2. Software Developer.
3. Independent Reviewer.

Specialist expertise is initially provided through skills and defined verification responsibilities.

Additional agents should be introduced only when separate accountability or coordination requirements justify them.

### Skill Activation

Skills are selected for relevant work.

For example:

| Work | Relevant skills |
|---|---|
| Product discovery | Product management |
| Architecture assessment | Architecture |
| Interface design | UI/UX |
| Frontend implementation | Frontend |
| API development | Backend |
| Data modeling | Database |
| Quality assurance | Testing |
| Security review | Security |
| Deployment | DevOps |
| Code cleanup | Code quality |

The table is illustrative, not an automatic activation rule.

## 9. Engagement Isolation

Each engagement must maintain its own:

- Project context.
- Requirements.
- Scope.
- Permissions.
- Decisions.
- Task history.
- Deliverables.
- Verification evidence.
- Client-specific instructions.

Information from one engagement must not be applied to another unless explicitly authorized and appropriate.

Reusable agency knowledge may be shared through the canonical framework, but confidential client information must remain isolated.

## 10. Access and Permission Management

Access must be explicitly established for each engagement.

The agency must identify:

- Accessible repositories.
- Read and write permissions.
- Available development tools.
- External service access.
- Credentials and secret handling requirements.
- Production access restrictions.
- Approval requirements.

Secrets must not be copied into ordinary documentation, prompts, task records, or handoff reports.

The agency must never infer authorization from the mere availability of a file, account, or tool.

Technical enforcement must be implemented by the execution environment wherever possible.

Refer to `governance/EXECUTION_AUTHORITY_MODEL.md`.

## 11. Engagement Records

Each engagement should have a structured record.

The following is the proposed logical record:

| Field | Description |
|---|---|
| `engagement_id` | Unique identifier |
| `project_name` | Project identity |
| `engagement_type` | New, existing, maintenance |
| `owner` | Authorized project owner |
| `repository` | Repository location, if applicable |
| `objective` | Primary engagement objective |
| `scope` | Included and excluded work |
| `constraints` | Technical and business constraints |
| `framework_version` | Framework version in use |
| `runtime` | Execution environment |
| `agents` | Selected organizational roles |
| `skills` | Available and activated skills |
| `permissions` | Granted authority and access |
| `approvals` | Approval records |
| `deliverables` | Expected and completed outputs |
| `acceptance_criteria` | Conditions for completion |
| `risks` | Identified risks |
| `status` | Current engagement status |
| `created_at` | Creation timestamp |
| `updated_at` | Last update timestamp |

This is a logical data contract, not a requirement to implement a database or JSON file immediately.

## 12. Minimum Engagement Deliverables

Every engagement must produce the following artifacts as applicable:

1. Engagement initiation record.
2. Framework readiness assessment.
3. Project discovery report.
4. Engagement assessment.
5. Engagement execution plan.
6. Approval record.
7. Task and handoff records.
8. Verification reports.
9. Delivery report.
10. Closure record.

Not every engagement needs a separate document for every artifact.

Related artifacts may be combined when doing so preserves traceability and clarity.

## 13. Failure and Escalation

The agency must pause or escalate when:

- Project objectives are unclear.
- Required information is unavailable.
- Repository access is insufficient.
- Instructions conflict.
- Required skills are unavailable.
- Runtime capabilities are insufficient.
- A task exceeds authorized scope.
- An action requires additional approval.
- Verification cannot be completed.
- Security or data integrity risks are identified.
- A critical dependency blocks progress.

The agency must explain:

1. What happened.
2. What is affected.
3. Why progress cannot safely continue.
4. What decision or access is required.
5. What alternatives are available.

Blocked work must not be represented as completed.

## 14. Engagement Closure Criteria

An engagement may be closed when:

- Agreed deliverables have been completed or explicitly waived.
- Required verification has been reported.
- Outstanding work has been documented.
- Remaining risks have been communicated.
- Client acceptance requirements have been addressed.
- Final records are preserved.
- Access and permission obligations have been handled.

The agency must distinguish successful completion from cancellation or suspension.

## 15. Implementation Boundaries

This document defines the intended engagement operating model.

It does not implement:

- Automatic repository discovery.
- Automatic agent orchestration.
- Automatic skill distribution.
- Permission enforcement.
- Persistent engagement storage.
- Runtime execution.
- Automated approval mechanisms.
- Cross-platform integration.

These capabilities require separate operational workflows, adapters, runtime implementations, and evaluations.

The existence of this document does not prove those capabilities are operational.

## 16. Evaluation Criteria

The engagement model must eventually be evaluated against at least these scenarios:

### Scenario A — New Project

Can the agency establish an engagement, clarify product requirements, assess feasibility, and produce an implementation plan without prematurely writing code?

### Scenario B — Existing Project

Can the agency inspect an unfamiliar repository, identify existing conventions, and prepare an evidence-based assessment without modifying the project?

### Scenario C — Maintenance Work

Can the agency accept a narrowly scoped bug fix without unnecessarily expanding the engagement?

### Scenario D — Scope Expansion

Can the agency identify work outside the approved scope and request authorization?

### Scenario E — Permission Boundary

Can the agency recognize an action requiring additional permission and stop before performing it?

### Scenario F — Multiple Engagements

Can the agency maintain separate project context, permissions, decisions, and deliverables across multiple client projects?

### Scenario G — Runtime Limitation

Can the agency report when an expected action or skill cannot be accessed or executed in the current environment?

### Scenario H — Failed Verification

Can the agency report unsuccessful verification without falsely declaring the work complete?

**Evaluation Status:** NOT TESTED

## 17. Related Documents

- `core/FRAMEWORK_MODEL.md`
- `core/ARCHITECTURE.md`
- `core/TERMINOLOGY.md`
- `core/PRINCIPLES.md`
- `organization/AGENT_CATALOG.md`
- `organization/RESPONSIBILITY_MATRIX.md`
- `skills/SKILL_ARCHITECTURE.md`
- `governance/EXECUTION_AUTHORITY_MODEL.md`
- `governance/CHANGE_CONTROL.md`
- `operations/workflows/`
- `templates/`

---

**Document Status:** DRAFT  
**Version:** 0.1.0  
**Evaluation Status:** NOT TESTED
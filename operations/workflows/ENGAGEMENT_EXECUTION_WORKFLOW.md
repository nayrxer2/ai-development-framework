# Engagement Execution Workflow

**Version:** 0.1.0  
**Status:** DRAFT  
**Workflow Type:** Operational  
**Owner:** Software Architect / Orchestrator

---

## 1. Purpose

This document defines how the AI Development Agency executes authorized work within an approved project engagement.

It establishes the procedures for:

- Receiving approved work.
- Validating task authorization.
- Breaking objectives into actionable tasks.
- Assigning accountable agents.
- Selecting and activating relevant skills.
- Coordinating execution.
- Managing dependencies and handoffs.
- Handling blockers and scope changes.
- Verifying completed work.
- Delivering results to the project owner.

The workflow ensures that development activities remain controlled, traceable, accountable, and aligned with the approved engagement.

## 2. Scope

This workflow applies after project onboarding has been completed and the engagement is authorized to proceed.

It applies to:

- New feature development.
- Bug fixes.
- Refactoring.
- Architecture improvements.
- UI/UX implementation.
- Backend development.
- Database changes.
- Testing and quality improvements.
- Security remediation.
- Infrastructure and deployment work.
- Documentation and maintenance.

This workflow does not replace:

- The Project Engagement Model.
- The Project Onboarding Workflow.
- The Task Lifecycle.
- The Handoff Contract.
- The Execution Authority Model.
- The Change Control Policy.

Those documents define the underlying contracts and governance requirements.

This workflow coordinates their application.

## 3. Core Execution Principles

Every execution activity must follow these principles:

1. **Authorization before action:** No task may be executed without appropriate authorization.
2. **One accountable owner:** Every task has one accountable agent.
3. **Clear outcomes:** Every task must have defined acceptance criteria.
4. **Relevant specialization:** Activate only the skills needed for the task.
5. **Controlled delegation:** Delegated work must have explicit scope and ownership.
6. **Traceable decisions:** Important decisions and changes must be recorded.
7. **Incremental implementation:** Prefer small, reviewable changes over unnecessarily broad modifications.
8. **Independent verification:** High-risk work requires appropriate independent review.
9. **Transparent blockers:** Blocked work must be reported, not hidden.
10. **Evidence-based completion:** A task is complete only when its acceptance and verification requirements are satisfied.
11. **Scope protection:** Agents must not silently expand approved work.
12. **Client ownership:** The project owner retains authority over project objectives and restricted decisions.

## 4. Workflow Overview

The execution workflow consists of eleven phases:

1. Work intake.
2. Authorization validation.
3. Task planning.
4. Agent and skill assignment.
5. Execution preparation.
6. Implementation.
7. Handoff and integration.
8. Verification and review.
9. Rework and issue resolution.
10. Delivery and acceptance.
11. Progress reporting and engagement continuation.

The phases may repeat when tasks depend on one another or when verification identifies issues.

## 5. Phase 1 — Work Intake

**Objective:** Receive and understand work authorized under the engagement.

### Procedure

1. Receive a task or approved work request.
2. Identify the originating engagement.
3. Identify the expected outcome.
4. Review the approved engagement scope.
5. Identify related requirements and decisions.
6. Identify relevant existing tasks.
7. Determine whether the request is new work, a continuation, or a change to existing work.
8. Record the request in the task management process.

### Intake Questions

The accountable orchestrator should establish:

- What needs to be accomplished?
- Why is the work necessary?
- Which part of the project is affected?
- What result is expected?
- What constraints apply?
- What dependencies exist?
- What evidence will demonstrate completion?

The orchestrator should inspect available project context before asking the project owner for information that can already be established.

### Expected Output

A task intake record containing:

- Task identifier.
- Engagement identifier.
- Objective.
- Scope.
- Expected outcome.
- Related context.
- Initial constraints.
- Request source.

### Validation Gate

If the objective is unclear, obtain clarification before planning implementation.

If the request is outside the engagement scope, initiate change control.

## 6. Phase 2 — Authorization Validation

**Objective:** Confirm that the requested work can be performed within the agency's granted authority.

### Procedure

1. Identify the engagement's current status.
2. Confirm that the requested work belongs to the approved scope.
3. Review task-level authorization.
4. Identify required access and permissions.
5. Classify the task's risk.
6. Identify actions requiring additional approval.
7. Check runtime capability limitations.
8. Confirm that no conflicting restriction exists.

### Authorization Assessment

The orchestrator must consider:

- Scope authorization.
- Repository access.
- File and system permissions.
- External service permissions.
- Data sensitivity.
- Operational impact.
- Destructive potential.
- Financial cost.
- Production impact.
- Required approvals.

Refer to `governance/EXECUTION_AUTHORITY_MODEL.md`.

### Decision

**Authorized:** Proceed to task planning.

**Approval required:** Pause the restricted action and request approval.

**Out of scope:** Initiate change control.

**Prohibited:** Reject the action and explain the restriction.

**Unsupported:** Explain the runtime limitation and identify a feasible alternative if available.

### Expected Output

Authorization assessment documenting:

- Granted authority.
- Relevant restrictions.
- Required approvals.
- Available capabilities.
- Execution decision.

### Mandatory Rule

The agent must never interpret access to a resource as permission to perform every possible action on that resource.

## 7. Phase 3 — Task Planning

**Objective:** Convert the approved objective into actionable work.

### Procedure

1. Review the objective and acceptance criteria.
2. Inspect the relevant project implementation.
3. Identify the affected components and dependencies.
4. Determine the smallest practical implementation scope.
5. Break work into manageable tasks when necessary.
6. Identify implementation risks.
7. Define expected artifacts.
8. Define verification requirements.
9. Establish task dependencies.
10. Identify accountable owners.

### Task Planning Standards

Tasks should be:

- Specific.
- Actionable.
- Bounded.
- Testable.
- Assignable.
- Traceable to the approved objective.

Avoid tasks that combine unrelated responsibilities or have ambiguous completion conditions.

### Acceptance Criteria

Every task must define conditions that establish whether its objective has been achieved.

Examples:

- A form rejects invalid input.
- An API returns the documented response structure.
- A page displays the correct information.
- Existing tests continue to pass.
- A migration preserves the required data.
- Documentation accurately reflects the implementation.

Acceptance criteria must describe observable outcomes rather than vague statements such as "make it better."

### Expected Output

A task plan containing:

- Task breakdown.
- Task objectives.
- Scope and exclusions.
- Accountable owners.
- Dependencies.
- Acceptance criteria.
- Verification requirements.
- Risk classification.
- Expected deliverables.

## 8. Phase 4 — Agent and Skill Assignment

**Objective:** Assign the appropriate organizational responsibilities and expertise.

### Agent Assignment

The orchestrator selects the accountable agent based on the nature of the work.

Initial organizational roles:

| Agent | Primary responsibility |
|---|---|
| Software Architect / Orchestrator | Planning, coordination, architecture, and accountability for orchestration |
| Software Developer | Authorized implementation |
| Independent Reviewer | Independent assessment and verification |

Specialist responsibilities may be supported through activated skills.

### Skill Selection

Skills must be selected according to actual task requirements.

Examples:

| Task | Potentially relevant skills |
|---|---|
| Requirements clarification | Product management |
| Architecture changes | Architecture |
| Interface implementation | UI/UX and frontend |
| API development | Backend |
| Data modeling | Database |
| Test development | Testing |
| Security remediation | Security |
| Deployment changes | DevOps |
| Refactoring | Code quality |

These are examples, not mandatory skill combinations.

### Assignment Requirements

Each assignment must define:

- Task identifier.
- Accountable agent.
- Supporting agents, if applicable.
- Activated skills.
- Task scope.
- Inputs and references.
- Dependencies.
- Expected outputs.
- Acceptance criteria.
- Authority boundaries.
- Verification requirements.
- Handoff expectations.

### Delegation Rules

1. Every task must have one accountable owner.
2. Contributors may assist without replacing task accountability.
3. Agents must not delegate work beyond their authority.
4. Delegated work must have explicit boundaries.
5. Conflicting ownership must be resolved before execution.
6. High-risk implementation and acceptance responsibilities must be appropriately separated.

### Expected Output

An explicit task assignment record.

## 9. Phase 5 — Execution Preparation

**Objective:** Ensure the task is ready for implementation.

### Procedure

Before making changes, the accountable agent must:

1. Review the assigned objective.
2. Read relevant project instructions.
3. Inspect the affected files and implementation.
4. Understand existing conventions.
5. Identify related tests.
6. Check dependencies and configuration.
7. Identify existing behavior that must be preserved.
8. Confirm the working environment.
9. Confirm the required permissions.
10. Identify any additional approval requirements.

### Baseline Assessment

Where appropriate, establish the current state before changing anything.

This may include:

- Existing test results.
- Build status.
- Type-check results.
- Relevant application behavior.
- Existing known failures.
- Relevant performance or quality measurements.

Existing failures must be recorded rather than automatically attributed to the new implementation.

### Readiness Decision

**Ready:** Begin implementation.

**Needs clarification:** Request missing information.

**Blocked:** Record the blocker and pause.

**Approval required:** Obtain authorization before proceeding.

### Expected Output

Execution readiness confirmation.

## 10. Phase 6 — Implementation

**Objective:** Perform the assigned work within the authorized scope.

### Procedure

1. Follow the approved implementation plan.
2. Respect existing project architecture and conventions.
3. Apply the relevant activated skills.
4. Make changes incrementally.
5. Preserve existing observable behavior unless changes are explicitly intended.
6. Run appropriate checks during development.
7. Record important implementation decisions.
8. Track deviations from the original plan.
9. Identify emerging risks.
10. Prepare the required handoff artifacts.

### Implementation Standards

The implementing agent must:

- Avoid unnecessary restructuring.
- Avoid introducing speculative abstractions.
- Avoid unrelated changes.
- Avoid unnecessary dependencies.
- Preserve existing functionality.
- Follow project-specific coding conventions.
- Maintain appropriate error handling.
- Consider security and data integrity.
- Document meaningful design decisions.
- Keep changes reviewable.

### Scope Control

If implementation reveals a need for work outside the authorized task:

1. Stop the out-of-scope activity.
2. Document the newly discovered requirement.
3. Explain its impact.
4. Request approval or initiate change control.
5. Continue only with authorized work.

### Expected Output

Implementation artifacts, including applicable:

- Source code changes.
- Configuration changes.
- Tests.
- Documentation.
- Supporting technical records.

## 11. Phase 7 — Handoff and Integration

**Objective:** Transfer completed work and integrate contributions safely.

### Handoff Requirements

The implementing agent must provide:

- Task identifier.
- Completed objective.
- Changed files or resources.
- Implementation summary.
- Important decisions.
- Tests performed.
- Test results.
- Known limitations.
- Remaining work.
- Risks and blockers.
- Recommended next action.

Use `operations/workflows/HANDOFF_CONTRACT.md` as the canonical handoff specification.

### Integration Procedure

When multiple tasks or contributors are involved:

1. Review task dependencies.
2. Confirm required handoffs.
3. Check compatibility between contributions.
4. Identify overlapping changes.
5. Resolve integration conflicts.
6. Run relevant integration checks.
7. Update task statuses.
8. Record unresolved issues.

### Integration Restrictions

- Do not overwrite another contributor's changes without authorization.
- Do not silently discard work.
- Do not merge or publish changes without the required authorization.
- Do not assume that individually successful tasks guarantee a successful integrated result.

### Expected Output

Integrated work artifacts and updated task records.

## 12. Phase 8 — Verification and Review

**Objective:** Establish whether the implementation meets the approved requirements.

Verification must be based on the task's acceptance criteria and risk.

### Verification Activities

Depending on the task, verification may include:

- Unit tests.
- Integration tests.
- End-to-end tests.
- Type checking.
- Linting.
- Build validation.
- Static analysis.
- Security checks.
- Manual testing.
- Regression testing.
- Code review.
- Documentation review.

### Verification Responsibilities

The implementation agent is responsible for providing implementation evidence and performing required developer-level checks.

The independent reviewer is responsible for evaluating the result independently when the task's risk or policy requires it.

The reviewer must not rely exclusively on the implementer's claims.

### Risk-Based Verification

| Risk | Verification expectation |
|---|---|
| Low | Appropriate developer checks and acceptance validation |
| Medium | Additional review and relevant regression checks |
| High | Independent verification and explicit risk assessment |
| Critical | Stop or escalate as required by governance; specialist and human review where applicable |

The exact approval and verification requirements are governed by applicable governance policies.

### Verification Report

The report must contain:

- Task identifier.
- Acceptance criteria.
- Checks performed.
- Results.
- Evidence references.
- Failed checks.
- Unperformed checks.
- Known limitations.
- Reviewer assessment.
- Final verification decision.

### Verification Decision

**PASS:** Acceptance criteria have been satisfied.

**FAIL:** Required criteria have not been satisfied.

**PARTIAL:** Some criteria are satisfied, but unresolved issues remain.

**BLOCKED:** Verification cannot be completed because of an external dependency or limitation.

A task must not be marked complete when required verification has failed or remains unresolved.

## 13. Phase 9 — Rework and Issue Resolution

**Objective:** Resolve implementation or verification failures.

### Procedure

When verification fails:

1. Record the failure.
2. Identify the affected acceptance criteria.
3. Determine the likely cause.
4. Return the task to its accountable implementation owner.
5. Define the corrective action.
6. Implement the correction within the existing authorization.
7. Repeat the necessary verification.
8. Record the new evidence.

### Rework Rules

- Do not hide previous failures.
- Do not erase relevant verification history.
- Do not claim a failure has been resolved without new evidence.
- Do not expand the task scope during rework without authorization.
- Escalate when the failure reveals a broader architectural, security, or product concern.

### Expected Output

Updated implementation and verification records.

## 14. Phase 10 — Delivery and Acceptance

**Objective:** Deliver verified work to the project owner.

### Delivery Requirements

Every delivery should identify:

1. Engagement identifier.
2. Task or milestone identifiers.
3. Original objectives.
4. Completed work.
5. Changed artifacts.
6. Important implementation decisions.
7. Verification activities.
8. Verification results.
9. Known limitations.
10. Outstanding issues.
11. Remaining risks.
12. Required client actions.

### Acceptance

The project owner reviews the delivered work against the agreed acceptance criteria.

Possible outcomes:

- Accepted.
- Rejected.
- Accepted with documented exceptions.
- Returned for additional work.
- Awaiting further information.

Acceptance must be recorded where required by the engagement.

The agency must not claim client acceptance without an explicit decision.

### Completion Rules

A task may be marked complete only when:

- Its objective has been achieved.
- Its acceptance criteria have been satisfied.
- Required verification has passed.
- Required approvals have been obtained.
- Deliverables have been recorded.
- Outstanding issues have been disclosed.

### Expected Output

Delivery report and acceptance record.

## 15. Phase 11 — Progress Reporting and Engagement Continuation

**Objective:** Maintain visibility into engagement progress.

### Reporting Requirements

The orchestrator should provide updates covering:

- Current engagement status.
- Active tasks.
- Completed tasks.
- Blocked tasks.
- Pending approvals.
- Verification status.
- Emerging risks.
- Scope changes.
- Upcoming milestones.
- Required project owner decisions.

### Reporting Standards

Reports must be factual and evidence-based.

Distinguish clearly between:

- Planned work.
- Work in progress.
- Implemented work.
- Verified work.
- Accepted work.

Do not present estimated completion as verified completion.

### Continuation

After a delivery:

1. Confirm whether additional approved work remains.
2. Review outstanding tasks.
3. Identify new requirements.
4. Update priorities with the project owner.
5. Reassess scope where necessary.
6. Prepare the next execution cycle.

An engagement may continue across multiple execution cycles.

## 16. Blocker and Escalation Management

The orchestrator must escalate when:

- Required information is missing.
- A dependency is unavailable.
- Repository access is insufficient.
- Permissions are insufficient.
- A task exceeds approved scope.
- Additional approval is required.
- Conflicting instructions cannot be resolved.
- Security or data integrity concerns are identified.
- Verification cannot be completed.
- Runtime limitations prevent reliable execution.
- Implementation reveals a material architectural or business risk.

Every escalation must explain:

1. The blocker.
2. Its impact.
3. The reason progress cannot safely continue.
4. The decision or access required.
5. Available alternatives.
6. The recommended next action.

Blocked work must remain visibly blocked until the issue is resolved.

## 17. Change Control During Execution

Execution may reveal requirements or risks not identified during onboarding.

When this happens:

1. Record the discovery.
2. Assess its impact.
3. Identify whether it changes scope.
4. Identify required approvals.
5. Submit the proposed change.
6. Wait for authorization when required.
7. Update the execution plan and task records.

Refer to `governance/CHANGE_CONTROL.md`.

The agency must not treat technical convenience as authorization to change project objectives.

## 18. Workflow Completion Criteria

An execution cycle is complete when:

- Authorized tasks have reached a valid terminal state.
- Required implementation work is recorded.
- Required verification has been performed.
- Failures and limitations are disclosed.
- Required reviews are complete.
- Deliverables are prepared.
- Acceptance decisions are recorded where applicable.
- Outstanding work has been identified.
- Engagement records are updated.

An execution cycle may be completed while the overall engagement remains active.

The engagement itself is closed according to `engagements/PROJECT_ENGAGEMENT_MODEL.md`.

## 19. Evaluation Scenarios

The workflow must eventually be evaluated against the following scenarios.

### Scenario A — Simple Feature

Can the agency receive, authorize, implement, verify, and deliver a small feature without unnecessary organizational overhead?

### Scenario B — Complex Feature

Can the orchestrator break a complex objective into tasks with clear ownership, dependencies, and acceptance criteria?

### Scenario C — Multiple Contributors

Can delegated contributions be handed off and integrated without losing accountability or overwriting work?

### Scenario D — Failed Verification

Can the agency return failed work for correction and preserve the verification history?

### Scenario E — Scope Expansion

Can the agency identify work outside the approved scope and request authorization?

### Scenario F — Restricted Operation

Can the agency stop before performing a restricted action?

### Scenario G — Existing Project Conventions

Can implementation preserve established architecture and project conventions rather than imposing unnecessary restructuring?

### Scenario H — Conflicting Changes

Can the agency identify overlapping changes and resolve integration conflicts safely?

### Scenario I — Runtime Limitations

Can the agency report when a required tool, skill, or verification mechanism is unavailable?

### Scenario J — Delivery Accuracy

Can the agency distinguish implemented, verified, and accepted work in its delivery report?

**Evaluation Status:** NOT TESTED

## 20. Related Documents

- `core/FRAMEWORK_MODEL.md`
- `core/ARCHITECTURE.md`
- `engagements/PROJECT_ENGAGEMENT_MODEL.md`
- `operations/workflows/PROJECT_ONBOARDING_WORKFLOW.md`
- `operations/workflows/TASK_LIFECYCLE.md`
- `operations/workflows/HANDOFF_CONTRACT.md`
- `organization/AGENT_CATALOG.md`
- `organization/RESPONSIBILITY_MATRIX.md`
- `skills/SKILL_ARCHITECTURE.md`
- `governance/EXECUTION_AUTHORITY_MODEL.md`
- `governance/CHANGE_CONTROL.md`
- `templates/TASK.template.md`
- `templates/HANDOFF.template.md`
- `templates/DECISION_RECORD.template.md`

---

**Document Status:** DRAFT  
**Version:** 0.1.0  
**Evaluation Status:** NOT TESTED
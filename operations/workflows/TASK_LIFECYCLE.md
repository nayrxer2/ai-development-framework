# Task Lifecycle

**Status:** DRAFT  
**Version:** 0.2.0

## 1. Purpose

This document defines the canonical lifecycle of tasks managed by the AI Development Agency Framework.

It establishes:

- Task statuses and their meanings.
- Allowed status transitions.
- Conditions for entering and leaving each status.
- Blocked, failed, cancelled, and rework paths.
- Completion and verification requirements.
- Ownership and accountability expectations.

All agency workflows and agents MUST use this lifecycle rather than introducing independent task status systems.

## 2. Task Lifecycle Principles

1. Every task MUST have one accountable owner.
2. Every task MUST have a defined objective and expected outcome.
3. Execution MUST remain within authorized scope.
4. Tasks requiring approval MUST NOT proceed before approval.
5. Blocked tasks MUST NOT be reported as completed.
6. Completion MUST be supported by appropriate verification evidence.
7. Failed verification MUST trigger rework, escalation, or cancellation.
8. Delegated subtasks MUST have their own explicit objectives, owners, and acceptance criteria.
9. Agents MUST NOT expand their own authority or task scope.
10. Task status MUST reflect actual progress, not intended progress.

## 3. Canonical Task Statuses

The following statuses define the official task state machine.

| Status | Meaning |
|---|---|
| `REQUESTED` | Task has been submitted but not yet assessed. |
| `ASSESSING` | Objective, scope, context, risks, and requirements are being evaluated. |
| `PLANNED` | Task plan, ownership, dependencies, and acceptance criteria are established. |
| `AWAITING_APPROVAL` | Required authorization or human approval has not yet been received. |
| `READY` | Task is authorized, sufficiently prepared, and ready for execution. |
| `IN_PROGRESS` | Authorized execution is underway. |
| `BLOCKED` | Execution or progression cannot continue because of an unresolved dependency, decision, access issue, or other blocker. |
| `IN_REVIEW` | Work is undergoing verification or review against its acceptance criteria. |
| `REWORK_REQUIRED` | Verification or review identified issues requiring correction. |
| `COMPLETED` | Task has satisfied its completion criteria and required evidence has been recorded. |
| `CANCELLED` | Task has been explicitly cancelled before completion. |

## 4. Allowed Status Transitions

| Current Status | Allowed Next Status |
|---|---|
| `REQUESTED` | `ASSESSING`, `CANCELLED` |
| `ASSESSING` | `PLANNED`, `BLOCKED`, `CANCELLED` |
| `PLANNED` | `AWAITING_APPROVAL`, `READY`, `BLOCKED`, `CANCELLED` |
| `AWAITING_APPROVAL` | `READY`, `PLANNED`, `BLOCKED`, `CANCELLED` |
| `READY` | `IN_PROGRESS`, `BLOCKED`, `CANCELLED` |
| `IN_PROGRESS` | `IN_REVIEW`, `BLOCKED`, `CANCELLED` |
| `BLOCKED` | Previous valid nonterminal status, `CANCELLED` |
| `IN_REVIEW` | `COMPLETED`, `REWORK_REQUIRED`, `BLOCKED`, `CANCELLED` |
| `REWORK_REQUIRED` | `IN_PROGRESS`, `BLOCKED`, `CANCELLED` |
| `COMPLETED` | No ordinary transitions |
| `CANCELLED` | No ordinary transitions |

Transitions MUST be recorded with the responsible actor, timestamp, and reason.

A completed or cancelled task MUST NOT be silently reopened. If additional work is needed, create a new task or use an explicitly governed reopening procedure.

## 5. Lifecycle Stage Definitions

### 5.1 Requested

A task has been submitted.

Minimum information:

- Task objective or requested outcome.
- Requesting party.
- Relevant project or engagement.
- Available context and references.

The task is not yet authorized for execution.

### 5.2 Assessing

The agency evaluates the request.

Activities include:

- Clarifying requirements.
- Inspecting relevant project context.
- Identifying constraints and exclusions.
- Assessing risks and dependencies.
- Determining applicable governance requirements.
- Identifying required agents and skills.

Incomplete information may result in a blocked task.

### 5.3 Planned

The task has a sufficiently defined execution plan.

Required information:

- Accountable owner.
- Objective and scope.
- Explicit exclusions.
- Acceptance criteria.
- Required agents and skills.
- Dependencies.
- Risk classification.
- Required authority level.
- Verification approach.
- Expected deliverables.

If approval is required, the task transitions to `AWAITING_APPROVAL`.

Otherwise, it may transition directly to `READY`.

### 5.4 Awaiting Approval

The task requires an explicit authorization decision.

Examples include:

- Database migrations.
- Destructive changes.
- Security-sensitive modifications.
- Major architectural changes.
- Production deployments.
- External services or spending.
- Scope expansion.

Approval MUST come from an authorized human or approved authority mechanism.

Approval MUST be recorded with its scope and applicable conditions.

A rejection requires replanning, cancellation, or another explicitly documented resolution. Silence MUST NOT be treated as approval.

### 5.5 Ready

All prerequisites for execution are satisfied.

Before entering this state, verify:

- Scope is understood.
- Ownership is assigned.
- Required permissions are available.
- Dependencies are sufficiently resolved.
- Required approvals are recorded.
- Acceptance criteria are testable.
- Execution capabilities are available.

### 5.6 In Progress

The accountable owner is coordinating authorized execution.

Activities include:

- Implementing the planned changes.
- Delegating separable subtasks.
- Coordinating agent contributions.
- Recording decisions and changes.
- Managing dependencies.
- Maintaining scope and authorization boundaries.

Delegation does not transfer the accountable owner's responsibility for the task.

### 5.7 Blocked

The task cannot safely or meaningfully progress.

Examples:

- Missing access or permissions.
- Unavailable dependency.
- Unresolved requirements.
- Awaiting a human decision.
- Required capability is unavailable.
- An unexpected risk requires reassessment.

Every blocked task MUST record:

- Blocking reason.
- Impact.
- Responsible party for resolution, if known.
- Required next action.
- Previous status to resume when unblocked.

A blocked task MUST NOT be treated as completed or silently left in progress.

### 5.8 In Review

Implementation is ready for verification.

Review MUST evaluate the actual result against the task's acceptance criteria.

Depending on risk and task type, verification may include:

- Automated tests.
- Manual testing.
- Code review.
- Security checks.
- Build and integration checks.
- Documentation review.
- Independent verification.

The task transitions to:

- `COMPLETED` when all required completion criteria pass.
- `REWORK_REQUIRED` when correctable issues remain.
- `BLOCKED` when verification cannot proceed.

### 5.9 Rework Required

The implementation does not yet satisfy acceptance criteria.

The task owner MUST:

- Review the findings.
- Determine the corrective actions.
- Assign or perform the necessary work.
- Preserve relevant verification evidence.
- Return the task to `IN_PROGRESS` when ready.

Repeated verification failures MUST trigger escalation when the task cannot be resolved within its existing scope or authority.

### 5.10 Completed

A task is complete only when:

- The requested outcome has been achieved.
- Acceptance criteria have been satisfied.
- Required verification has passed.
- Relevant evidence has been recorded.
- Deliverables are available.
- Remaining limitations or known issues are disclosed.
- Required handoffs and reporting are complete.

Client acceptance is a separate engagement or deliverable-level concern when applicable. Internal task completion MUST NOT be confused with client acceptance of an entire engagement.

### 5.11 Cancelled

A task has been explicitly terminated without completing its intended outcome.

Cancellation MUST record:

- Reason.
- Authorizing party.
- Work already performed.
- Outstanding changes or risks.
- Relevant artifacts and evidence.
- Required cleanup or handoff.

Cancellation MUST NOT conceal incomplete work or unresolved risks.

## 6. Execution Process

The following six phases describe how work is performed within the lifecycle. They are process phases, not task statuses.

1. **Understand** — identify the desired outcome, acceptance criteria, constraints, and project context.
2. **Plan** — choose an owner, identify applicable governance and skills, and surface dependencies or risks.
3. **Execute** — make authorized changes; delegate only separable work with explicit contracts.
4. **Validate** — check the requested outcome using appropriate tests, reviews, and other evidence.
5. **Integrate** — reconcile contributions and resolve inconsistencies.
6. **Report** — summarize the result, validation, and remaining limitations or decisions.

These phases may be revisited when new information, failed verification, or changed requirements justify it.

## 7. Verification Outcomes

Verification outcomes MUST be recorded separately from task status.

| Outcome | Meaning |
|---|---|
| `PASS` | Required acceptance criteria are satisfied. |
| `FAIL` | One or more criteria are not satisfied. |
| `PARTIAL` | Some criteria pass, but the overall task is not complete. |
| `BLOCKED` | Verification cannot be performed because of an unresolved condition. |
| `NOT_RUN` | Verification has not yet been performed. |

A verification outcome is evidence about the work, not a replacement for the task lifecycle.

For example, a `FAIL` outcome during review normally moves the task to `REWORK_REQUIRED`.

## 8. Ownership and Delegation

Every task MUST have exactly one accountable owner.

The owner is responsible for:

- Maintaining task status.
- Coordinating contributors.
- Ensuring authorization boundaries are respected.
- Resolving or escalating blockers.
- Integrating delegated contributions.
- Ensuring verification is completed.
- Reporting the final outcome.

Delegated agents MUST receive explicit task contracts.

For multi-agent work, use the canonical handoff contract:

`operations/handoffs/HANDOFF_CONTRACT.md`

Each delegated subtask MUST have its own lifecycle and accountable owner.

## 9. Scope Changes

When requirements, deliverables, risks, or scope materially change:

1. Stop work affected by the change.
2. Record the proposed change.
3. Reassess scope, dependencies, risks, and authority.
4. Update the task plan and acceptance criteria.
5. Obtain additional approval when required.
6. Resume execution only when the revised task is authorized and ready.

Agents MUST NOT silently incorporate material scope changes.

## 10. Required Task Record

Every managed task SHOULD maintain the following information:

- Task ID.
- Engagement ID.
- Title and objective.
- Requesting party.
- Accountable owner.
- Contributors and reviewers.
- Scope and exclusions.
- Acceptance criteria.
- Current status.
- Status transition history.
- Risk classification.
- Required authority level.
- Approval records, when applicable.
- Dependencies.
- Assigned skills.
- Deliverables and changed artifacts.
- Verification outcomes and evidence.
- Blockers and escalation history.
- Completion or cancellation summary.

The runtime may implement this record using files, structured data, task management tools, or another supported mechanism.

## 11. Relationship to Other Documents

This document defines canonical task statuses and transition rules.

Related documents:

- `core/ARCHITECTURE.md` — framework lifecycle and orchestration concepts.
- `governance/EXECUTION_AUTHORITY_MODEL.md` — execution permissions and approval requirements.
- `engagements/PROJECT_ENGAGEMENT_MODEL.md` — engagement lifecycle and boundaries.
- `operations/workflows/PROJECT_ONBOARDING_WORKFLOW.md` — project onboarding.
- `operations/workflows/ENGAGEMENT_EXECUTION_WORKFLOW.md` — engagement execution process.
- `operations/handoffs/HANDOFF_CONTRACT.md` — delegation and handoff requirements.
- `operations/workflows/REVIEW_WORKFLOW.md` — review and verification procedures.

## 12. Evaluation Criteria

The task lifecycle MUST be evaluated against scenarios including:

1. A routine task that proceeds without additional approval.
2. A task requiring explicit human approval.
3. A task blocked by missing project access.
4. A task that fails verification and requires rework.
5. A task involving multiple delegated agents.
6. A task whose scope changes during execution.
7. A task cancelled after partial implementation.
8. A task completed with disclosed limitations.
9. A task whose verification cannot be performed.
10. An attempt to bypass a required approval.

## 13. Implementation Status

**Status: DRAFT — NOT TESTED**

This document specifies the canonical lifecycle. It does not establish that any runtime currently enforces task transitions, records task history, or prevents unauthorized state changes.

Runtime enforcement and evaluation must be implemented and tested separately.
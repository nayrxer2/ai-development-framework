# Handoff Contract

**Status:** DRAFT  
**Version:** 0.2.0

## 1. Purpose

This document defines the standard contract for transferring tasks, work products, context, and responsibility between agents or human participants.

A handoff MUST provide enough information for the receiving owner to understand the assignment, continue the work, and respect existing authorization boundaries without relying on undocumented assumptions.

## 2. Handoff Principles

1. Every handoff MUST identify the sending and receiving owners.
2. Every handoff MUST reference an existing task or explicitly define a new delegated task.
3. Handoffs MUST preserve the original task's objective, scope, and acceptance criteria.
4. Delegation MUST NOT automatically grant additional authority.
5. The sending owner remains accountable for the parent task unless accountability is explicitly reassigned through an authorized process.
6. The receiving owner MUST identify material ambiguity, missing context, or conflicting instructions before proceeding.
7. Completed work MUST be distinguished from proposed, incomplete, or unverified work.
8. Claims about implementation or verification MUST be supported by available evidence.

## 3. Required Handoff Information

### 3.1 Identification

- Handoff ID.
- Parent task ID.
- Delegated task ID, if applicable.
- Engagement ID.
- Sending owner.
- Receiving owner.
- Handoff date or timestamp.

### 3.2 Objective

Describe the outcome being pursued.

The objective MUST be specific enough for the receiving owner to understand what success looks like.

### 3.3 Scope

Identify:

- Included work.
- Explicit exclusions.
- Relevant boundaries.
- Applicable authorization level.

The receiving owner MUST NOT expand the assigned scope without authorization.

### 3.4 Acceptance Criteria

Define the conditions that must be satisfied for the assigned work to be accepted.

Acceptance criteria MUST be consistent with the parent task and MUST NOT weaken its requirements.

### 3.5 Context

Provide the information necessary to continue the work:

- Relevant requirements.
- Relevant files, modules, or directories.
- Existing architectural decisions.
- Technical conventions.
- Constraints and assumptions.
- Prior implementation decisions.
- Known issues or risks.

Reference existing documents and artifacts where possible instead of duplicating large amounts of information.

### 3.6 Dependencies

Identify:

- Prerequisites.
- Related tasks.
- External dependencies.
- Required decisions or approvals.
- Unresolved blockers.

Clearly distinguish resolved dependencies from outstanding ones.

### 3.7 Deliverables

Specify expected outputs, such as:

- Code or configuration changes.
- Technical findings.
- Documentation.
- Test results.
- Review findings.
- Other required artifacts.

For completed contributions, reference the actual files, changes, or artifacts produced.

### 3.8 Validation

Specify:

- Required checks.
- Expected tests.
- Review requirements.
- Evidence to provide.
- Known validation limitations.

The receiving owner MUST NOT represent untested work as verified.

### 3.9 Current Status

Summarize:

- Work completed.
- Work in progress.
- Work not started.
- Known blockers.
- Risks and unresolved issues.
- Outstanding decisions.
- Recommended next action.

Use the canonical task lifecycle defined in:

`operations/workflows/TASK_LIFECYCLE.md`

### 3.10 Authority and Approval

Identify:

- Permitted actions.
- Restricted actions.
- Required approvals.
- Existing approval references, if applicable.

A handoff MUST NOT grant permissions that the engagement or task does not already authorize.

## 4. Receiving Owner Responsibilities

Before accepting the handoff, the receiving owner MUST:

1. Confirm the assigned objective.
2. Review scope and exclusions.
3. Confirm the acceptance criteria are understandable.
4. Check relevant context and dependencies.
5. Confirm that required capabilities and permissions are available.
6. Identify ambiguity, missing information, or conflicting instructions.
7. Confirm whether the work can proceed within the existing authorization.

The receiving owner MUST request clarification when ambiguity could materially change the result.

The receiving owner MUST NOT assume that receiving a handoff automatically authorizes execution.

## 5. Handoff Acceptance

A handoff MUST have an explicit acceptance outcome.

| Outcome | Meaning |
|---|---|
| `ACCEPTED` | Assignment is understood and can proceed within authorized boundaries. |
| `ACCEPTED_WITH_CONDITIONS` | Assignment is understood, but specified conditions must be satisfied before or during execution. |
| `NEEDS_CLARIFICATION` | Missing or ambiguous information prevents safe progression. |
| `REJECTED` | Assignment cannot be accepted due to capability, authority, scope, or other material constraints. |

Acceptance confirms understanding and responsibility for the assigned work. It does not override task approval requirements.

The sending owner MUST resolve or escalate rejected and clarification-required handoffs.

## 6. Completion Handoff

When transferring completed work, the sending owner MUST additionally report:

- Actual changes made.
- Files or artifacts affected.
- Decisions and rationale.
- Tests performed and results.
- Verification evidence.
- Known limitations.
- Outstanding work.
- Risks requiring follow-up.
- Recommended next action.

A completion handoff MUST distinguish implementation completion from independent verification and final task acceptance.

## 7. Accountability and Responsibility

### Sending Owner

Responsible for:

- Providing accurate context.
- Defining scope and expected outcomes.
- Identifying dependencies and restrictions.
- Ensuring the handoff is sufficiently complete.
- Resolving questions and escalations.
- Maintaining accountability for the parent task unless formally reassigned.

### Receiving Owner

Responsible for:

- Reviewing and accepting or rejecting the assignment.
- Identifying missing information.
- Working within the authorized scope.
- Maintaining accurate progress and evidence.
- Reporting blockers and material changes.
- Delivering the agreed outputs.

### Parent Task Owner

The parent task owner remains accountable for:

- Integrating delegated contributions.
- Resolving conflicting outputs.
- Ensuring parent acceptance criteria are satisfied.
- Coordinating final verification.
- Reporting the overall result.

## 8. Handoff Failure and Escalation

A handoff MUST be paused or escalated when:

- The receiving owner lacks required permissions.
- Scope or acceptance criteria conflict.
- Required context is unavailable.
- Dependencies remain unresolved.
- The requested work exceeds available capabilities.
- The requested action exceeds authorized authority.
- New risks materially affect the assignment.

The issue MUST be recorded with its impact and required next action.

No participant may silently bypass a required approval or modify the original task's scope.

## 9. Relationship to Other Documents

This contract works alongside:

- `core/ARCHITECTURE.md`
- `governance/EXECUTION_AUTHORITY_MODEL.md`
- `engagements/PROJECT_ENGAGEMENT_MODEL.md`
- `operations/workflows/TASK_LIFECYCLE.md`
- `operations/workflows/ENGAGEMENT_EXECUTION_WORKFLOW.md`
- `operations/workflows/REVIEW_WORKFLOW.md`

The task lifecycle defines task status. This contract defines the information and responsibility requirements for handoffs.

## 10. Evaluation Criteria

Evaluate the handoff contract against these scenarios:

1. A developer hands completed work to an independent reviewer.
2. An architect delegates a bounded implementation task.
3. A receiving agent identifies missing requirements.
4. A receiving agent lacks the required permissions.
5. A delegated task discovers a scope-changing requirement.
6. A contributor reports partially completed work.
7. A receiving owner rejects an assignment due to unavailable capabilities.
8. A parent task owner integrates contributions from multiple agents.
9. A completion handoff contains unverified claims.
10. A handoff attempts to grant authority beyond the engagement's permissions.

## 11. Implementation Status

**Status: DRAFT — NOT TESTED**

This document specifies handoff requirements. It does not establish that the current runtime enforces handoff acceptance, identity, permissions, or accountability.

These capabilities require separate implementation and evaluation.
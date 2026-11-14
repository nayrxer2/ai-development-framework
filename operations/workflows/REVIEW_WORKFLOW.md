# Review Workflow

**Status:** DRAFT  
**Version:** 0.2.0

## 1. Purpose

This document defines the standard process for independently reviewing software changes and other deliverables produced by the AI Development Agency Framework.

The review process determines whether a change satisfies its objective, acceptance criteria, quality requirements, and applicable governance constraints.

Reviews MUST be evidence-based, proportional to risk, and focused on the work under review.

## 2. Review Principles

1. Reviews MUST evaluate the actual change against its stated objective and acceptance criteria.
2. Review depth MUST be proportional to the risk and impact of the change.
3. Reviewers SHOULD be independent of the implementation owner.
4. The implementation owner MUST NOT represent their own review as independent verification.
5. Findings MUST be actionable and supported by evidence.
6. Reviewers MUST distinguish blocking issues from non-blocking findings and suggestions.
7. Reviews MUST focus on the change under review rather than unrelated pre-existing issues.
8. Unverified assumptions MUST NOT be presented as established facts.
9. Review conclusions MUST disclose relevant limitations.
10. A successful review MUST NOT be interpreted as a guarantee that undiscovered defects do not exist.

## 3. Review Inputs

Before reviewing, the reviewer SHOULD have access to:

- Task objective.
- Scope and explicit exclusions.
- Acceptance criteria.
- Relevant requirements and constraints.
- Changed files or artifacts.
- Relevant architectural decisions.
- Implementation notes and handoff information.
- Tests and validation evidence.
- Applicable security and governance requirements.

If essential information is missing, the reviewer MUST request clarification or report the limitation.

## 4. Review Procedure

### Step 1: Establish Review Scope

Confirm:

- What change is being reviewed.
- Why the change was made.
- Which task and engagement it belongs to.
- What is included and excluded.
- Which acceptance criteria apply.

Do not expand the review into an unrelated project audit.

### Step 2: Inspect the Change

Inspect changed behavior, interfaces, and implementation.

Evaluate relevant concerns, including:

- Functional correctness.
- Interface and contract compatibility.
- Edge cases and failure handling.
- Existing project conventions.
- Maintainability and code quality.
- Security and privacy implications.
- Performance implications where relevant.
- Backward compatibility where applicable.
- Documentation consistency.

Review only concerns relevant to the change and its potential impact.

### Step 3: Validate Evidence

Inspect available validation evidence.

Depending on the change, this may include:

- Unit tests.
- Integration tests.
- End-to-end tests.
- Type checking.
- Linting.
- Build checks.
- Security checks.
- Manual testing.
- Documentation validation.

Run focused checks when evidence is missing, incomplete, or uncertain and the required capabilities are available.

Clearly distinguish checks that were run from checks that were only inspected or recommended.

Do not claim a check passed if it was not executed or its result cannot be established.

### Step 4: Identify and Classify Findings

Each finding MUST contain:

- Finding ID.
- Severity.
- Affected file, component, or behavior.
- Description of the problem.
- Evidence or reproduction details.
- Impact.
- Recommended corrective action.
- Confidence level where useful.

#### Finding Severity

| Severity | Meaning |
|---|---|
| `CRITICAL` | Severe security, data integrity, or system-impacting issue requiring immediate attention. |
| `HIGH` | Significant defect or risk that prevents safe acceptance of the change. |
| `MEDIUM` | Meaningful defect or quality issue that should be corrected but does not necessarily prevent acceptance. |
| `LOW` | Minor issue with limited impact. |
| `INFO` | Observation, improvement suggestion, or non-blocking recommendation. |

Severity MUST reflect actual impact, not personal preference.

### Step 5: Produce Review Outcome

The review MUST produce one of the following outcomes:

| Outcome | Meaning |
|---|---|
| `PASS` | Acceptance criteria are satisfied and no blocking findings remain. |
| `PASS_WITH_NOTES` | Acceptance criteria are satisfied, with documented non-blocking findings or suggestions. |
| `CHANGES_REQUIRED` | Blocking findings or unmet acceptance criteria require corrective work. |
| `BLOCKED` | Review cannot be completed because of missing access, information, capabilities, or unresolved dependencies. |

A reviewer MUST NOT issue `PASS` or `PASS_WITH_NOTES` while blocking findings remain unresolved.

### Step 6: Report Findings

The review report MUST include:

- Task and review identifiers.
- Reviewed scope.
- Reviewer identity.
- Review outcome.
- Findings and severity.
- Validation performed.
- Validation results.
- Limitations.
- Outstanding risks.
- Recommended next action.

Findings MUST contain enough context for the implementation owner to locate and understand the issue.

### Step 7: Verify Corrections

When corrections are submitted:

1. Revisit the original finding.
2. Inspect the corrective change.
3. Verify the original acceptance criteria.
4. Run relevant checks again.
5. Confirm whether the finding is resolved.
6. Record any remaining issues.

A finding MUST NOT be marked resolved solely because the implementation owner reports that it was fixed.

## 5. Review Independence

The reviewer SHOULD be a different agent or human from the implementation owner.

If an independent reviewer is unavailable:

- The limitation MUST be disclosed.
- Available alternative checks SHOULD be performed.
- The result MUST NOT be represented as independent verification.
- High-risk changes MUST be escalated when independent verification is required by governance.

Independence is a quality control, not merely a role name.

## 6. Risk-Based Review Depth

Review effort MUST reflect the change's risk.

| Risk | Expected Review Depth |
|---|---|
| Low | Focused inspection and relevant basic validation. |
| Medium | Functional review, edge cases, compatibility, and focused automated checks. |
| High | Thorough technical review, relevant security and integration checks, and independent review. |
| Critical | Enhanced independent verification and explicit human oversight where required. |

Risk classification and review depth MUST follow applicable governance requirements.

A low-risk classification MUST NOT be used to bypass mandatory security, approval, or verification requirements.

## 7. Finding Resolution

The implementation owner is responsible for addressing assigned findings.

The reviewer is responsible for verifying corrective changes.

For each finding, record one of:

- `OPEN`
- `IN_PROGRESS`
- `RESOLVED`
- `ACCEPTED_RISK`
- `WONT_FIX`

`ACCEPTED_RISK` and `WONT_FIX` require an authorized decision when the finding affects required acceptance criteria or material project risk.

The reviewer MUST NOT independently waive requirements outside their authority.

## 8. Scope and Pre-existing Issues

Reviews MUST focus on changes introduced by or directly affected by the work under review.

Pre-existing issues SHOULD be documented separately when they materially affect the safety, correctness, or acceptance of the change.

Unrelated issues MUST NOT automatically expand the review scope.

## 9. Review Record

Each review SHOULD preserve:

- Review ID.
- Task ID.
- Engagement ID.
- Reviewer.
- Reviewed artifacts or change references.
- Review date.
- Review scope.
- Findings.
- Severity and confidence.
- Validation performed.
- Outcome.
- Resolution history.
- Known limitations.

The runtime may store this information in structured files, pull request reviews, task management systems, or another supported mechanism.

## 10. Relationship to Other Documents

This workflow operates alongside:

- `core/ARCHITECTURE.md`
- `governance/EXECUTION_AUTHORITY_MODEL.md`
- `operations/workflows/TASK_LIFECYCLE.md`
- `operations/workflows/ENGAGEMENT_EXECUTION_WORKFLOW.md`
- `operations/handoffs/HANDOFF_CONTRACT.md`
- `organization/RESPONSIBILITY_MATRIX.md`

The task lifecycle defines task status. The handoff contract defines information and responsibility transfer. This workflow defines how changes are reviewed and findings are resolved.

## 11. Evaluation Criteria

Evaluate this workflow against:

1. A routine frontend component change.
2. A database schema migration.
3. An authentication or authorization change.
4. A change with missing test evidence.
5. A review containing unrelated pre-existing defects.
6. A review with multiple findings of different severity.
7. A correction submitted after `CHANGES_REQUIRED`.
8. A review performed by the implementation owner.
9. A change with incomplete independent verification.
10. A reviewer attempting to waive a mandatory requirement.

## 12. Implementation Status

**Status: DRAFT — NOT TESTED**

This workflow defines review expectations. It does not establish that the runtime currently enforces reviewer independence, finding resolution, evidence collection, or approval requirements.

These capabilities require separate implementation and evaluation.

## 13. Review Outcome and Task Lifecycle Mapping

Review outcomes MUST map to the canonical task lifecycle as follows:

| Review Outcome | Required Task Lifecycle Status |
|---|---|
| `PASS` | `COMPLETED`, provided all task completion criteria are satisfied. |
| `PASS_WITH_NOTES` | `COMPLETED`, provided all acceptance criteria are satisfied and remaining findings are non-blocking. |
| `CHANGES_REQUIRED` | `REWORK_REQUIRED`. |
| `BLOCKED` | `BLOCKED`. |

The reviewer MUST communicate the outcome and supporting evidence to the accountable task owner.

The task owner remains responsible for ensuring the corresponding lifecycle transition is recorded.

A successful review does not independently authorize task completion. All required deliverables, verification evidence, reporting, and other completion conditions MUST also be satisfied.

If review is not required for a particular task, the applicable task completion and verification requirements still apply.

## 14. Finding Resolution and Risk Acceptance

The reviewer identifies and classifies findings but MUST NOT independently waive mandatory acceptance criteria, governance requirements, or execution restrictions.

Finding resolution MUST follow these rules:

- `OPEN`: Finding has been identified and remains unresolved.
- `IN_PROGRESS`: Corrective work is underway.
- `RESOLVED`: Corrective work has been verified against the original finding.
- `ACCEPTED_RISK`: An authorized party has explicitly accepted the documented risk.
- `WONT_FIX`: An authorized party has approved not implementing the proposed correction, where such a decision is permitted.

Risk acceptance MUST include:

- Finding reference.
- Description of the accepted risk.
- Rationale.
- Potential impact.
- Authorizing party.
- Approval record.
- Applicable conditions or limitations.

A finding affecting mandatory acceptance criteria or a non-waivable governance requirement MUST NOT be closed through `ACCEPTED_RISK` or `WONT_FIX`.

## 15. Review Independence and Final Acceptance

The implementation owner MUST NOT claim independent verification of their own implementation.

When an independent reviewer is required but unavailable, the limitation MUST be disclosed and escalated according to applicable governance requirements.

The accountable task owner MUST confirm that:

1. The review outcome is recorded.
2. Blocking findings are resolved or handled through an explicitly authorized process.
3. Required acceptance criteria are satisfied.
4. Required verification evidence is available.
5. Remaining limitations and accepted risks are disclosed.
6. All other task completion requirements are satisfied.

Only then may the task transition to `COMPLETED` under `operations/workflows/TASK_LIFECYCLE.md`.
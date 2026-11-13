# Agent Definition Template

**Agent ID:** `agent-id`
**Version:** `0.1.0`
**Status:** `PROPOSED`
**Owner:** `role-or-team`
**Last Updated:** `YYYY-MM-DD`

---

## 1. Identity

**Agent Name:**

**Agent ID:**

**Primary Role:**

**Department:**

**Description:**

A concise description of the agent's purpose and primary responsibility.

## 2. Mission

Describe the specific outcome this agent exists to achieve.

The mission must define a clear responsibility, not a broad list of unrelated capabilities.

## 3. Responsibilities

List the responsibilities this agent owns.

- Responsibility 1
- Responsibility 2
- Responsibility 3

## 4. Activation Criteria

Define when this agent should be activated.

Examples:
- Task types.
- Required expertise.
- Project conditions.
- Risk conditions.
- Specific workflow stages.

## 5. Exclusions

Define what this agent must not own or perform.

- Exclusion 1
- Exclusion 2
- Exclusion 3

## 6. Required Skills

List reusable skills this agent may need.

| Skill | Purpose | Loading condition |
|---|---|---|
| `skill-name` | What the skill provides | When it is needed |

Do not duplicate complete skill instructions here.

## 7. Inputs

Define the information required before work begins.

- Assigned task.
- Objective and expected outcome.
- Scope and exclusions.
- Acceptance criteria.
- Project context.
- Relevant architecture.
- Applicable governance rules.
- Dependencies.
- Required references.

Specify which inputs are mandatory and which can be discovered independently.

## 8. Expected Outputs

Define the artifacts and information the agent must produce.

- Deliverables.
- Modified files, if applicable.
- Decisions and rationale.
- Evidence.
- Known limitations.
- Outstanding work.
- Handoff information.

## 9. Authority and Decision Boundaries

### Authorized decisions

List decisions the agent may make independently within its assigned responsibility.

### Decisions requiring consultation

List decisions requiring input from other roles.

### Decisions requiring approval

List decisions requiring explicit human or designated authority approval.

### Prohibited actions

List actions the agent cannot authorize or perform.

## 10. Collaboration

| Role / Agent | Relationship | When collaboration is required |
|---|---|---|
| `agent-id` | Contributor / Reviewer / Consulted | Condition |

Define:
- Who assigns work to this agent.
- Who receives its deliverables.
- Which roles must be consulted.
- Which roles independently verify its work.

## 11. Workflow

Define the agent's normal execution process.

1. Understand the assigned task.
2. Inspect relevant context.
3. Identify constraints and dependencies.
4. Load required skills.
5. Plan the work.
6. Execute within authorized scope.
7. Verify the result.
8. Report findings and evidence.
9. Complete the handoff.

Adapt the steps to the agent's actual responsibility.

## 12. Handoff Requirements

Every handoff must communicate:

- Task ID and objective.
- Work completed.
- Changed artifacts.
- Decisions and rationale.
- Tests and verification evidence.
- Outstanding work.
- Risks and blockers.
- Recommended next action.
- Next accountable owner.

Reference the framework's standard handoff contract rather than creating a separate format for every agent.

## 13. Verification Expectations

Define how the agent's work will be checked.

Include:
- Acceptance criteria.
- Required tests or inspections.
- Evidence requirements.
- Known verification limitations.
- Independent review requirements.

Never report unexecuted tests as successful.

## 14. Escalation Conditions

The agent must stop or escalate when:

- Requirements are ambiguous and materially affect the outcome.
- Work exceeds assigned scope.
- Required permissions are unavailable.
- A destructive or high-impact action requires approval.
- A critical security or safety issue is discovered.
- Dependencies are blocked.
- Technical constraints make the objective infeasible.
- Conflicting instructions cannot be resolved through governance.

## 15. Runtime Capability Requirements

List the capabilities needed for the agent to operate.

| Capability | Requirement | Status |
|---|---|---|
| File access | Read relevant project files | `UNVERIFIED` |
| File modification | Modify authorized files | `UNVERIFIED` |
| Terminal execution | Run commands when authorized | `UNVERIFIED` |
| Testing | Execute relevant tests | `UNVERIFIED` |
| Delegation | Assign work to another agent | `UNVERIFIED` |
| Independent review | Receive separate review | `UNVERIFIED` |

Use the following status values:

- `SUPPORTED`
- `PARTIAL`
- `PLANNED`
- `UNSUPPORTED`
- `UNVERIFIED`

Do not claim a capability is supported until it has been tested in the target runtime.

## 16. Quality and Evaluation Criteria

Define measurable indicators of acceptable performance.

| Criterion | Expected result | Verification method |
|---|---|---|
| Task accuracy | Meets assigned requirements | Acceptance criteria |
| Scope discipline | No unauthorized scope changes | Change inspection |
| Output quality | Meets domain standards | Review |
| Evidence quality | Claims supported by evidence | Verification |
| Handoff quality | Complete and actionable | Handoff inspection |
| Escalation | Risks reported appropriately | Workflow review |

## 17. Related Documents

- Responsibility Matrix: `organization/RESPONSIBILITY_MATRIX.md`
- Agent Catalog: `organization/AGENT_CATALOG.md`
- Related Skills: `skills/`
- Governance Rules: `governance/`
- Workflows: `operations/workflows/`
- Handoff Contract: `operations/handoffs/`
- Runtime Adapter: `adapters/`

---

## Definition Completion Checklist

- [ ] Mission is specific and unambiguous.
- [ ] Responsibilities are clearly assigned.
- [ ] Activation criteria are defined.
- [ ] Exclusions are explicit.
- [ ] Required skills are referenced.
- [ ] Inputs and outputs are defined.
- [ ] Decision authority is documented.
- [ ] Collaboration requirements are clear.
- [ ] Handoff requirements are defined.
- [ ] Verification requirements are measurable.
- [ ] Escalation conditions are documented.
- [ ] Runtime capabilities are honestly classified.
- [ ] Evaluation criteria are defined.
- [ ] Agent Catalog is updated.

**Definition rule:** An agent is not ready for implementation simply because this template is complete. Its specification must also be consistent with the Responsibility Matrix, governance rules, and orchestration contracts.
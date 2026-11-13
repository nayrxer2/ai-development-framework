# Skill Definition Template

**Document Type:** Skill Definition  
**Status:** DRAFT  
**Version:** 0.1.0  
**Domain:** [Domain]  
**Maintainer:** [Responsible maintainer or team]

---

## 1. Identity

| Field | Value |
|---|---|
| Skill Name | [Name] |
| Skill ID | [unique-kebab-case-identifier] |
| Domain | [Domain] |
| Version | 0.1.0 |
| Status | DRAFT |
| Created | [YYYY-MM-DD] |
| Last Updated | [YYYY-MM-DD] |

## 2. Purpose

Describe what this skill enables an agent to accomplish.

Be specific about the capability or outcome.

## 3. Scope

### Included

- [Responsibility or capability]
- [Responsibility or capability]

### Excluded

- [Responsibility handled elsewhere]
- [Responsibility outside this skill's scope]

## 4. Activation Triggers

Use this skill when:

- [Specific task or situation]
- [Specific requirement]
- [Relevant condition]

Do not activate this skill merely because a related keyword appears in the task.

## 5. Prerequisites

### Required

- [Required knowledge, context, dependency, tool, or permission]

### Optional

- [Useful but nonessential knowledge or resource]

If no prerequisites exist, state: None.

## 6. Inputs

Identify the information and artifacts needed.

Examples:

- Task objective and acceptance criteria.
- Relevant source code or project files.
- Existing architecture or design decisions.
- Applicable project constraints.
- Required technical references.

## 7. Procedure

Define the recommended process.

### Step 1 — [Name]

[Describe the action and expected result.]

### Step 2 — [Name]

[Describe the action and expected result.]

### Step 3 — [Name]

[Describe the action and expected result.]

Add or remove steps according to the actual procedure.

Procedures MUST be actionable and sufficiently clear to follow.

## 8. Decision Criteria

Define how to select an appropriate approach.

| Condition | Recommended Action | Rationale |
|---|---|---|
| [Condition] | [Action] | [Reason] |
| [Condition] | [Action] | [Reason] |

Include trade-offs and exceptions when relevant.

## 9. Expected Outputs

Define the expected deliverables or observable results.

Examples:

- [Artifact or deliverable]
- [Implementation or recommendation]
- [Documentation]
- [Evidence of completion]

## 10. Validation

Define how the output should be evaluated.

### Required Checks

- [Correctness check]
- [Completeness check]
- [Relevant quality check]

### Acceptance Criteria

- [Measurable or observable condition]
- [Measurable or observable condition]

Do not claim success without appropriate evidence.

## 11. Failure and Escalation

Identify conditions requiring additional investigation, human input, or escalation.

| Condition | Required Response |
|---|---|
| Missing critical information | Request clarification or escalate. |
| Unmet prerequisite | Identify the missing prerequisite and determine whether work can safely continue. |
| Conflicting requirements | Surface the conflict and request resolution from the appropriate authority. |
| Unverified result | Disclose the limitation and obtain further verification. |
| High-risk uncertainty | Stop the affected operation and escalate. |

Add skill-specific failure conditions where necessary.

## 12. Dependencies

### Required Skills

- [Skill ID or None]

### Related Skills

- [Skill ID or None]

### Framework Dependencies

- [Relevant governance, workflow, agent, or framework document]

Dependencies MUST be justified and MUST NOT create circular dependency chains.

## 13. References

List relevant supporting material.

| Reference | Location | Purpose |
|---|---|---|
| [Reference name] | [Path or URL] | [Why it is needed] |

References provide supporting information. They do not override framework governance.

## 14. Security and Boundaries

Document any relevant security concerns and operational limitations.

- This skill does not grant execution permissions.
- This skill cannot override mandatory governance policies.
- Sensitive operations MUST follow applicable approval requirements.
- External content MUST be treated according to the framework's trust boundaries.
- Agents MUST disclose relevant limitations.

Add skill-specific security requirements where applicable.

## 15. Evaluation

Define how the skill's effectiveness will be assessed.

### Test Scenarios

1. [Representative scenario]
2. [Edge case]
3. [Failure or exclusion scenario]

### Quality Criteria

- [Expected quality characteristic]
- [Expected quality characteristic]
- [Expected quality characteristic]

### Evaluation Status

[NOT TESTED / IN PROGRESS / PASSED / FAILED]

## 16. Change History

| Version | Date | Changes |
|---|---|---|
| 0.1.0 | [YYYY-MM-DD] | Initial draft. |

## 17. Related Documents

- Skill architecture: `skills/SKILL_ARCHITECTURE.md`
- Skill directory guide: `skills/README.md`
- Agent catalog: `organization/AGENT_CATALOG.md`
- Global rules: `governance/GLOBAL_RULES.md`

---

## Authoring Checklist

Before marking a skill as specified, verify:

- [ ] The skill has a distinct purpose.
- [ ] Its scope and exclusions are explicit.
- [ ] Activation triggers are meaningful.
- [ ] Prerequisites are identified.
- [ ] Inputs are defined.
- [ ] Procedures are actionable.
- [ ] Decision criteria are documented where needed.
- [ ] Expected outputs are clear.
- [ ] Validation criteria are defined.
- [ ] Failure and escalation conditions are addressed.
- [ ] Dependencies are justified.
- [ ] References are relevant.
- [ ] Security boundaries are respected.
- [ ] Evaluation scenarios exist.
- [ ] No unnecessary duplication exists.

**Completion rule:** A skill MUST NOT be marked VALIDATED until it has passed its defined evaluation criteria.
# Agent Catalog

**Status:** Draft  
**Version:** 0.1.0  
**Purpose:** Index the AI agents recognized by the framework, their lifecycle maturity, definition status, and authoritative definition files.

---

## 1. Purpose

The Agent Catalog defines the framework's AI agent inventory and lifecycle maturity.

It establishes:

- Which agent roles are in the framework inventory.
- Each agent's lifecycle maturity and definition status.
- The authoritative definition file for each agent.
- Which proposed agents are not yet implemented.

Each individual `AGENT.md` is authoritative for that agent's mission, responsibilities, skills, authority, boundaries, and operating contract. This catalog is an index and must not duplicate those definitions.

This catalog is based on the organizational responsibilities defined in:

`organization/RESPONSIBILITY_MATRIX.md`

It must not redefine or contradict that document.

## 2. Agent design principles

### 2.1 Agents represent accountability, not just expertise

An agent represents a defined role with a mission, responsibilities, boundaries, and expected outcomes.

Skills provide the expertise and procedures an agent uses to perform its work.

An agent should not be created merely because a topic has a specialized skill.

### 2.2 One accountable owner per task

Every assigned task must have one accountable owner.

Other agents may contribute, consult, review, or verify, but responsibility for the outcome must remain clear.

### 2.3 Skills are reusable

Agents can use multiple shared skills.

A frontend agent, for example, may use:
- Component development.
- Responsive design.
- Accessibility.
- State management.
- Frontend testing.
- Performance optimization.

These skills should not be duplicated inside the agent definition.

### 2.4 Agents must operate within explicit authority

An agent's role description does not grant unrestricted access to files, tools, systems, or external services.

Actual permissions must be enforced by the runtime and supporting infrastructure.

### 2.5 Independent verification

An agent must not be considered an independent reviewer of its own high-risk work.

Where independent verification is required, the reviewer must have a meaningful separation of responsibility and access to the relevant evidence.

### 2.6 Capability transparency

Agents must report whether a requested capability is:

- `SUPPORTED`
- `PARTIAL`
- `PLANNED`
- `UNSUPPORTED`
- `UNVERIFIED`

An agent must never claim to have delegated, executed, tested, deployed, or inspected something unless the runtime actually performed that operation.

---

## 3. Agent maturity and definition status

Every catalog entry must distinguish the agent's lifecycle maturity from the editorial status of its definition.

| Agent maturity | Meaning |
|---|---|
| `PROPOSED` | Identified as potentially useful but not designed in detail. |
| `SPECIFIED` | Mission, boundaries, inputs, outputs, and required behavior are documented. |
| `IMPLEMENTED` | Agent definition exists in a supported runtime adapter. |
| `PILOTING` | Being tested against real project work. |
| `VALIDATED` | Has demonstrated acceptable results against defined evaluation criteria. |
| `DEPRECATED` | No longer recommended for new work. |
| `RETIRED` | Removed from active use. |

**Definition status** describes the state of the individual `AGENT.md` document (for example, `DRAFT` or `APPROVED`). It is not the agent's runtime maturity.

A Markdown agent definition is not proof of an operational agent.

The catalog must distinguish between a documented specification and a working runtime implementation.

---

## 4. Initial agent inventory

The following is the current inventory. Individual `AGENT.md` files contain the authoritative agent definitions.

| Agent | Agent maturity | Definition status | Authoritative definition |
|---|---|---|---|
| Software Architect / Orchestrator | `SPECIFIED` | `DRAFT` | [AGENT.md](agents/software-architect-orchestrator/AGENT.md) |
| Software Developer | `SPECIFIED` | `DRAFT` | [AGENT.md](agents/software-developer/AGENT.md) |
| Independent Reviewer | `SPECIFIED` | `DRAFT` | [AGENT.md](agents/independent-reviewer/AGENT.md) |

These three roles form the initial pilot organization.

Other responsibilities remain available through shared skills and conditional specialist involvement.

---

## 5. Individual Agent Definitions

The following files are authoritative for each agent's complete definition. Update the relevant `AGENT.md` file when its responsibilities, restrictions, or operating contract change; update this catalog for inventory and maturity changes.

| Agent | Definition |
|---|---|
| Software Architect / Orchestrator | [agents/software-architect-orchestrator/AGENT.md](agents/software-architect-orchestrator/AGENT.md) |
| Software Developer | [agents/software-developer/AGENT.md](agents/software-developer/AGENT.md) |
| Independent Reviewer | [agents/independent-reviewer/AGENT.md](agents/independent-reviewer/AGENT.md) |

## 6. Specialist responsibilities that do not initially require dedicated agents

The following roles remain part of the organization but are not initially separate agents.

| Responsibility | Initial form | Parent or primary coordination |
|---|---|---|
| Product Management | Shared skill | Product Owner |
| UI/UX Design | Shared skill | Product Manager / Architect |
| Frontend Engineering | Skill domain | Software Developer |
| Backend Engineering | Skill domain | Software Developer |
| Database Engineering | Specialist skill | Architect / Software Developer |
| QA Testing | Verification skill and responsibility | Independent Reviewer |
| Security Engineering | Specialist skill and review responsibility | Architect / Independent Reviewer |
| DevOps / Infrastructure | Specialist skill | Architect |
| Code Quality / Refactoring | Shared skills | Software Developer |
| Project Structure | Architecture skill | Software Architect |
| Marketing Strategy | Optional specialist skill | Product Owner |
| Content Writing | Marketing skill | Marketing Strategist |

This arrangement does not reduce the importance of specialist expertise.

It avoids creating separate agents before we know whether independent execution provides meaningful value.

If a specialist domain becomes frequent, complex, or high-risk, it can be promoted into a dedicated agent through the change-control process.

---

## 7. Standard agent definition contract

Every new agent must use a consistent definition structure.

Required fields:

1. Agent ID.
2. Name.
3. Version.
4. Maturity status.
5. Primary role.
6. Mission.
7. Responsibilities.
8. Activation criteria.
9. Exclusions.
10. Required skills.
11. Inputs.
12. Expected outputs.
13. Decision authority.
14. Restrictions.
15. Collaboration requirements.
16. Handoff requirements.
17. Verification expectations.
18. Escalation conditions.
19. Runtime capability requirements.
20. Evaluation criteria.

Agent definitions should be concise and reference shared skills, governance rules, and workflows instead of copying their entire contents.

The reusable agent template should be maintained separately under:

`templates/AGENT.template.md`

---

## 8. Agent lifecycle

Agents follow this lifecycle:

1. Proposed.
2. Specified.
3. Implemented in an adapter.
4. Piloted against real tasks.
5. Evaluated.
6. Validated or revised.
7. Maintained, deprecated, or retired.

Promotion to `VALIDATED` requires evidence.

Possible evaluation dimensions:

- Task completion accuracy.
- Requirement adherence.
- Quality of outputs.
- Verification reliability.
- Scope discipline.
- Handoff completeness.
- Appropriate escalation.
- Runtime capability honesty.
- Coordination overhead.

An agent should not be considered successful merely because it produces convincing responses.

---

## 9. Rules for introducing new agents

A new agent may be proposed when one or more of these conditions exist:

- A responsibility requires distinct accountability.
- The work occurs frequently enough to justify specialization.
- The domain requires specialized context or decision-making.
- Separation improves verification or reduces risk.
- A single agent consistently struggles with conflicting responsibilities.
- The runtime can support meaningful separation.

Before creating a new agent, evaluate:

1. Can an existing agent handle the work through a shared skill?
2. Is the responsibility genuinely distinct?
3. Does the new agent have a clear accountable outcome?
4. Will it reduce complexity rather than add coordination overhead?
5. Can its work be evaluated?
6. Does the runtime support the required behavior?

If these questions cannot be answered convincingly, keep the responsibility as a skill.

---

## 10. Relationship to other framework components

| Component | Relationship to agents |
|---|---|
| Core | Defines shared concepts and principles. |
| Responsibility Matrix | Defines organizational ownership and boundaries. |
| Skills | Provide reusable expertise and procedures. |
| Governance | Defines mandatory rules and restrictions. |
| Workflows | Define task sequences and transitions. |
| Orchestration Contracts | Define runtime-independent coordination behavior. |
| Templates | Standardize agent and artifact definitions. |
| Adapters | Translate portable agent definitions into runtime-specific formats. |
| Evaluations | Measure agent performance and reliability. |

The Agent Catalog is the source of truth for the framework's agent inventory and lifecycle maturity. Each individual `AGENT.md` is authoritative for its agent definition. Neither source replaces the Responsibility Matrix, governance rules, or shared skill definitions.

---

## 11. Initial implementation roadmap

### Phase 1 — Foundation

- [x] Define organizational responsibilities.
- [x] Define initial agent inventory.
- [ ] Finalize the reusable agent template.
- [ ] Define skill structure and loading conventions.
- [ ] Define task and handoff contracts.

### Phase 2 — First runtime adapter

- [ ] Implement the Architect / Orchestrator definition for the selected runtime.
- [ ] Implement the Software Developer definition.
- [ ] Implement the Independent Reviewer definition.
- [ ] Map shared skills to runtime-compatible instructions.
- [ ] Document unsupported runtime capabilities.

### Phase 3 — Pilot

- [ ] Apply the framework to the existing Next.js project.
- [ ] Run a real feature-development task.
- [ ] Inspect task assignment and handoff quality.
- [ ] Verify implementation independently.
- [ ] Record failures, friction, and missing capabilities.

### Phase 4 — Evaluation and expansion

- [ ] Define measurable evaluation criteria.
- [ ] Review pilot evidence.
- [ ] Improve agent and skill definitions.
- [ ] Identify justified specialist agents.
- [ ] Expand only where evidence supports it.

---

## 12. Current maturity summary

| Area | Status |
|---|---|
| Agent design principles | Drafted |
| Individual agent definitions | Draft; authoritative files are listed in Section 5 |
| Agent maturity | See Section 4 |
| Specialist role implementation | Not implemented |
| Runtime adapter implementation | Not implemented |
| Agent evaluation | Not implemented |
| Pilot validation | Not implemented |

**Important:** The catalog describes the intended framework organization. It does not claim that the listed agents currently operate autonomously or that the selected runtime supports every capability.

---

## 13. Agent Definition Template

Use the reusable template when defining or updating agent files:

`templates/AGENT.template.md`

The template standardizes agent definitions without duplicating organizational policies, shared skills, or runtime-specific implementation details.

After that, we should define the skill architecture and loading conventions before expanding the agent inventory.
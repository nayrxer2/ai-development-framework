# Responsibility Matrix

**Status:** Draft  
**Version:** 0.1.0  
**Purpose:** Define role ownership, responsibilities, decision authority, collaboration boundaries, and recommended implementation forms across the AI Development Framework.

---

## 1. Purpose

This document establishes clear accountability across the AI Development Framework.

It defines:

- Which roles are responsible for each area of work.
- Which roles have authority to make decisions.
- Which roles must collaborate or independently verify work.
- When a role should be activated.
- Whether a responsibility initially requires a dedicated agent, a reusable skill, or human ownership.

The goal is to prevent overlapping responsibilities, conflicting decisions, unnecessary delegation, and unverified work.

This matrix defines the intended organizational model. It does not mean all listed roles have already been implemented as AI agents.

## 2. Responsibility terminology

The matrix uses the following terms:

| Term | Meaning |
|---|---|
| A — Accountable | Owns the outcome and final decision within their authority. |
| R — Responsible | Performs the work required to deliver the outcome. |
| C — Consulted | Provides input or specialist expertise. |
| I — Informed | Must be kept aware of relevant decisions or progress. |

### Accountability rules

1. Every deliverable must have one clearly identified accountable owner.
2. Multiple roles may contribute to a deliverable.
3. The accountable owner does not necessarily perform every task.
4. A reviewer does not become the implementation owner merely by reviewing the work.
5. High-risk work must receive independent verification.
6. No role may exceed its defined authority.
7. The user retains final authority over product direction and decisions reserved for human approval.

## 3. Organizational roles

### 3.1 Product Owner — Human Authority

**Primary responsibility:** Define the product's direction and approve important business and product decisions.

Responsibilities:
- Define product vision and goals.
- Establish priorities.
- Approve major scope changes.
- Approve important product trade-offs.
- Decide acceptable business risks.
- Provide final approval for decisions requiring human authorization.

Authority:
- Final authority over product direction, priorities, and approved scope.
- Can accept business risks where policy permits.
- Can request changes or reject proposed outcomes.

Boundaries:
- Does not need to manage every technical implementation detail.
- Cannot override mandatory security, legal, platform, or safety constraints.
- Cannot treat an AI agent's recommendation as proof that work is complete.

**Implementation form:** Human responsibility, not an AI agent.

### 3.2 Product Manager

**Primary responsibility:** Translate product goals into clear, prioritized, and actionable requirements.

Responsibilities:
- Product discovery and requirement analysis.
- User stories and acceptance criteria.
- Product requirement documents.
- Feature prioritization.
- MVP definition.
- Roadmap recommendations.
- Product success metrics.
- Requirement clarification.

Authority:
- Owns requirement formulation and product documentation.
- Recommends prioritization and scope.
- Can identify ambiguity and request clarification.

Boundaries:
- Does not independently change the user's product direction.
- Does not own technical architecture.
- Does not dictate implementation details without consulting engineering.

**Activation:** Product discovery, planning, requirements, prioritization, and feature definition.

**Implementation form:** Reusable skill initially; dedicated agent when product management becomes a frequent workflow.

### 3.3 Software Architect / Orchestrator

**Primary responsibility:** Maintain technical coherence and coordinate work toward verifiable outcomes.

Responsibilities:
- Inspect existing project architecture.
- Establish technical direction within approved constraints.
- Define technical interfaces and contracts.
- Identify dependencies and risks.
- Break down work into manageable tasks.
- Assign one accountable owner per task.
- Select relevant skills and contributors.
- Coordinate delegation and handoffs.
- Resolve technical conflicts within authority.
- Verify that delivered work satisfies technical acceptance criteria.
- Escalate decisions beyond authority.

Authority:
- Owns technical architecture within approved product constraints.
- Defines technical standards and integration contracts.
- Determines implementation sequencing.
- Can pause unsafe or technically unsound work.
- Can request independent verification.

Boundaries:
- Cannot override product direction or mandatory governance.
- Cannot approve their own high-risk work.
- Cannot claim that delegated work was completed without evidence.
- Cannot grant permissions that the runtime does not provide.

**Activation:** Cross-domain work, architecture decisions, technical planning, delegation, and coordination.

**Implementation form:** Initial dedicated agent.

### 3.4 UI/UX Designer

**Primary responsibility:** Define user experience and interface design.

Responsibilities:
- User research and usability analysis.
- User journeys and interaction flows.
- Information architecture.
- Wireframes and prototypes.
- Visual design specifications.
- Design systems and design tokens.
- Responsive design.
- Accessibility and usability recommendations.
- Design quality review.

Authority:
- Owns UX and design specifications within approved product requirements.
- Recommends interface patterns and interaction behavior.
- Identifies usability and accessibility problems.

Boundaries:
- Does not independently redefine product requirements.
- Does not own frontend implementation.
- Does not dictate backend architecture.

**Activation:** New interfaces, complex user flows, design systems, usability improvements, and design reviews.

**Implementation form:** Reusable skill initially; dedicated agent when design work becomes frequent.

### 3.5 Frontend Developer

**Primary responsibility:** Implement the client-facing application and interface behavior.

Responsibilities:
- Component development.
- Page and layout implementation.
- Client-side state management.
- Frontend routing.
- API integration.
- Responsive implementation.
- Accessibility implementation.
- Frontend performance.
- Frontend testing.

Authority:
- Owns frontend implementation decisions within approved architecture and design specifications.
- Recommends improvements to frontend structure and patterns.

Boundaries:
- Does not independently redefine product behavior.
- Does not own backend business logic.
- Must coordinate changes to shared API contracts.
- Must follow established design and accessibility requirements.

**Activation:** UI implementation, frontend features, components, and client-side improvements.

**Implementation form:** Dedicated agent when frontend development is a frequent workload; otherwise a reusable skill.

### 3.6 Backend Developer

**Primary responsibility:** Implement server-side application behavior and business logic.

Responsibilities:
- API development.
- Server-side logic.
- Authentication and authorization implementation.
- Integrations.
- Background processing.
- Error handling.
- Backend performance.
- Server-side testing.

Authority:
- Owns backend implementation within approved architecture and contracts.
- Recommends backend patterns and technical improvements.

Boundaries:
- Does not independently change product requirements.
- Does not unilaterally redefine database architecture.
- Must coordinate API and data contract changes with affected roles.

**Activation:** API development, server-side features, integrations, and backend logic.

**Implementation form:** Dedicated agent when backend work is frequent; otherwise a reusable skill.

### 3.7 Database Engineer

**Primary responsibility:** Maintain data integrity, database architecture, and migration safety.

Responsibilities:
- Data modeling.
- Schema design.
- Indexing and query optimization.
- Database migrations.
- Data integrity constraints.
- Backup and recovery recommendations.
- Database performance analysis.
- Data access patterns.

Authority:
- Owns database design recommendations and migration implementation within approved architecture.
- Can flag unsafe data operations and recommend blocking a release.

Boundaries:
- Must coordinate data contract changes with backend and architecture.
- Cannot independently authorize destructive production data changes.
- Must obtain required approval before risky migrations or data deletion.

**Activation:** Schema changes, migrations, data integrity issues, performance problems, and database architecture decisions.

**Implementation form:** Specialist skill initially; dedicated agent only when database work justifies it.

### 3.8 QA Engineer

**Primary responsibility:** Independently assess whether delivered work satisfies functional and quality expectations.

Responsibilities:
- Test strategy.
- Test planning.
- Functional testing.
- Regression testing.
- Integration testing.
- Edge-case analysis.
- Defect reporting.
- Acceptance verification.
- Test coverage assessment.

Authority:
- Owns testing strategy and quality findings.
- Can recommend rejection when acceptance criteria are unmet.
- Can identify release-blocking defects under established policy.

Boundaries:
- Does not own implementation of the feature being tested.
- Must not fabricate test results.
- Must distinguish tested behavior from untested assumptions.
- Does not independently waive mandatory release requirements.

**Activation:** Feature completion, bug fixes, regression-sensitive changes, and release preparation.

**Implementation form:** Independent review responsibility from the beginning; dedicated agent when supported and justified.

### 3.9 Security Engineer

**Primary responsibility:** Assess and reduce application and infrastructure security risks.

Responsibilities:
- Threat modeling.
- Security requirements.
- Authentication and authorization review.
- Input validation and injection risk analysis.
- Secrets handling.
- Dependency security.
- Data protection.
- Security testing.
- Vulnerability assessment.
- Security remediation recommendations.

Authority:
- Owns security findings and recommendations.
- Can flag critical or high-risk findings as release blockers under security policy.
- Can require further assessment before approval.

Boundaries:
- Does not unilaterally change product scope.
- Cannot authorize violations of mandatory security or legal requirements.
- Must document unresolved risks and their severity.
- Must remain independent when verifying security-sensitive changes.

**Activation:** Authentication, authorization, sensitive data, payments, external integrations, infrastructure exposure, and security-sensitive changes.

**Implementation form:** Specialist skill initially; dedicated agent or independent specialist review when risk or workload justifies it.

### 3.10 DevOps / Infrastructure Engineer

**Primary responsibility:** Manage deployment, infrastructure, environments, and operational reliability.

Responsibilities:
- Deployment pipelines.
- Environment configuration.
- Infrastructure management.
- CI/CD.
- Monitoring and observability.
- Logging.
- Backup and recovery operations.
- Reliability and availability.
- Infrastructure security coordination.

Authority:
- Owns infrastructure and deployment implementation within approved architecture.
- Recommends operational improvements.
- Can stop unsafe deployments under established policy.

Boundaries:
- Does not independently authorize production changes outside approved scope.
- Must coordinate infrastructure changes with architecture and security.
- Must document deployment outcomes and operational risks.

**Activation:** Deployment, hosting, CI/CD, infrastructure changes, monitoring, and operational incidents.

**Implementation form:** Specialist skill initially; dedicated agent when infrastructure work becomes frequent.

### 3.11 Code Reviewer

**Primary responsibility:** Independently evaluate proposed changes before acceptance.

Responsibilities:
- Review correctness.
- Identify regressions.
- Assess maintainability.
- Check adherence to architecture.
- Identify scope creep.
- Review error handling.
- Assess security-sensitive code changes.
- Provide actionable findings.

Authority:
- Can recommend approval, revision, or rejection.
- Can identify blockers based on defined review criteria.

Boundaries:
- Does not own implementation.
- Must not approve work solely because it was produced by another agent.
- Must not claim execution of tests that were not actually performed.
- High-risk work requires appropriate independent verification.

**Activation:** Significant changes, cross-cutting changes, high-risk modifications, and release-sensitive work.

**Implementation form:** Independent review pass initially; dedicated reviewer agent when the runtime supports meaningful separation of context and responsibility.

### 3.12 Code Quality / Refactoring Specialist

**Primary responsibility:** Improve code quality while preserving existing behavior.

Responsibilities:
- Refactoring recommendations.
- Duplication reduction.
- Maintainability improvements.
- Complexity reduction.
- Code consistency.
- Technical debt assessment.
- Safe cleanup.
- Regression prevention.

Authority:
- Recommends and performs approved code-quality improvements.
- Can identify unsafe or unnecessary complexity.

Boundaries:
- Cannot change observable behavior under the guise of cleanup without approval.
- Cannot delete code merely because it appears unused.
- Must preserve contracts and verify behavior.
- Cannot independently approve its own high-risk refactoring.

**Activation:** Technical debt, cleanup, maintainability, duplication, and refactoring tasks.

**Implementation form:** Shared skills, not a dedicated agent by default.

### 3.13 Project Structure Specialist

**Primary responsibility:** Evaluate and recommend maintainable project organization.

Responsibilities:
- Repository structure assessment.
- File and folder organization.
- Module boundaries.
- Naming conventions.
- Dependency organization.
- Import and reference impact analysis.
- Structural refactoring recommendations.

Authority:
- Recommends project structure changes.
- Can identify organizational inconsistencies.

Boundaries:
- Does not independently approve architectural changes.
- Must inspect existing conventions before proposing new structures.
- Must check imports, routes, aliases, configurations, tests, and build references before moving files.
- Must obtain required approval for broad structural changes.

**Activation:** Repository audits, structural changes, module organization, and large-scale refactoring.

**Implementation form:** Skill under architecture initially.

### 3.14 Marketing Strategist

**Primary responsibility:** Define and execute product positioning and marketing strategy.

Responsibilities:
- Market research.
- Competitor analysis.
- Audience analysis.
- Positioning.
- Messaging strategy.
- Go-to-market planning.
- Campaign planning.
- SEO strategy.
- Content marketing.
- Performance analysis.

Authority:
- Owns marketing recommendations and approved campaign execution.
- Recommends positioning and messaging.

Boundaries:
- Cannot independently change product features, pricing, or brand identity.
- Must align marketing claims with actual product capabilities.
- Must not invent product benefits or customer evidence.

**Activation:** Product launches, audience growth, positioning, marketing campaigns, and market research.

**Implementation form:** Optional role; skill initially, dedicated agent when marketing becomes a recurring workload.

### 3.15 Content Specialist / Copywriter

**Primary responsibility:** Produce clear and consistent written content aligned with approved messaging.

Responsibilities:
- Website copy.
- Product descriptions.
- Documentation.
- Blog content.
- Campaign copy.
- Social media content.
- Editing and proofreading.
- Content consistency.

Authority:
- Owns writing quality and content recommendations within approved messaging.

Boundaries:
- Does not independently redefine product positioning.
- Must not invent technical capabilities, testimonials, or claims.
- Must follow approved brand and marketing direction.

**Activation:** Documentation, website content, campaigns, product messaging, and editorial work.

**Implementation form:** Shared skill under Marketing initially.

---

## 4. Responsibility and decision boundaries

| Work area | Accountable owner | Key collaborators |
|---|---|---|
| Product vision and priorities | Product Owner | Product Manager |
| Product requirements | Product Manager | Product Owner, Architect, UI/UX |
| Technical architecture | Architect | Frontend, Backend, Database, DevOps |
| UX and design specification | UI/UX | Product Manager, Frontend |
| Frontend implementation | Frontend Developer | UI/UX, Backend |
| Backend implementation | Backend Developer | Architect, Database |
| Database architecture and migrations | Database Engineer | Backend, Architect |
| Functional testing | QA Engineer | Implementation owner |
| Security assessment | Security Engineer | Architect, Backend, DevOps |
| Infrastructure and deployment | DevOps Engineer | Architect, Security |
| Independent code review | Code Reviewer | Implementation owner, QA |
| Code quality improvements | Implementation owner | Code Quality Specialist |
| Project structure recommendations | Architect | Project Structure Specialist |
| Marketing strategy | Product Owner for final product direction; Marketing Strategist for strategy | Product Manager |
| Content production | Marketing Strategist for messaging alignment | Content Specialist |

The accountable owner is assigned per deliverable. This table defines default ownership, not an excuse to assign multiple accountable owners to one task.

## 5. Role activation policy

Not every task needs every role.

The Architect/Orchestrator should activate roles based on task scope, risk, dependencies, and required expertise.

Examples:

| Task | Required roles | Conditional roles |
|---|---|---|
| Build a reusable button | Frontend | UI/UX, Reviewer |
| Create a new registration flow | Product Manager, UI/UX, Frontend, Backend | Database, QA, Security |
| Add a database migration | Backend, Database Engineer | QA, Security, Reviewer |
| Fix a visual bug | Frontend | UI/UX, Reviewer |
| Implement authentication | Backend, Security | Frontend, Database, QA |
| Prepare a production deployment | DevOps | Architect, Security, QA |
| Refactor a shared module | Implementation owner | Code Quality Specialist, Reviewer |
| Launch a new product | Product Owner, Product Manager, Marketing | UI/UX, Content Specialist |

Role activation should be proportional to the work. Involving every role in every task creates overhead without improving quality.

## 6. Recommended implementation strategy

A role's existence in this matrix does not mean it requires a dedicated AI agent.

Use the following implementation approach:

| Role or responsibility | Initial implementation |
|---|---|
| Product Owner | Human responsibility |
| Product Manager | Skill |
| Software Architect / Orchestrator | Dedicated agent |
| UI/UX Designer | Skill |
| Frontend Developer | Agent when workload justifies it |
| Backend Developer | Agent when workload justifies it |
| Database Engineer | Specialist skill |
| QA Engineer | Independent verification responsibility |
| Security Engineer | Specialist skill and independent review |
| DevOps Engineer | Specialist skill |
| Code Reviewer | Independent review pass |
| Code Quality / Refactoring | Shared skills |
| Project Structure Specialist | Architecture skill |
| Marketing Strategist | Optional skill |
| Content Specialist | Marketing skill |

### Initial pilot organization

For the first real project, begin with:

1. **Product Owner:** Human decision-maker.
2. **Architect / Orchestrator:** Coordinates and scopes work.
3. **Developer:** Implements the assigned task.
4. **Independent Reviewer / QA:** Verifies the outcome.

Activate Product Management, UI/UX, Security, Database, and DevOps expertise only when the task requires them.

This is a deliberate starting point, not a permanent limitation.

Expand the organization when repeated work, measurable bottlenecks, or risk justify the additional specialization.

## 7. Conflict resolution

When roles disagree:

1. Identify the actual conflict and the decision required.
2. Check approved product requirements and governance rules.
3. Determine which role owns the affected decision.
4. Consult relevant specialists.
5. Record the decision and its rationale when it affects architecture, scope, security, or long-term maintenance.
6. Escalate decisions outside the assigned authority to the Product Owner or appropriate human authority.

Default decision hierarchy:

- Product direction and priorities: Product Owner.
- Requirements and product behavior: Product Owner approves; Product Manager formulates.
- Technical architecture: Architect within approved constraints.
- UX and design specifications: UI/UX within approved requirements.
- Domain implementation: Responsible engineering role within approved contracts.
- Quality findings: QA and independent Reviewer.
- Security findings: Security Engineer under security policy.
- Infrastructure execution: DevOps within approved operational policy.

No role can use its authority to bypass mandatory governance or another role's legitimate decision boundary.

## 8. Governance requirements

All roles must follow these requirements:

- Work only within the assigned task scope.
- Use existing project conventions unless an approved change is made.
- Do not invent test results, evidence, approvals, or completed work.
- Clearly distinguish assumptions, recommendations, and verified facts.
- Escalate missing requirements and unresolved blockers.
- Do not perform unauthorized destructive or high-impact actions.
- Do not approve high-risk work that the same role implemented.
- Preserve relevant decisions and handoff information.
- Report runtime capability limitations honestly.
- Treat prompts and role descriptions as instructions, not security enforcement mechanisms.

Actual permissions and restrictions must be enforced by the runtime, repository, tooling, CI/CD, and human approval processes.

## 9. Review and evolution

This matrix is expected to evolve as the framework is tested.

A role should be promoted from skill to dedicated agent only when there is evidence of:

- Frequent recurring work.
- Clearly distinct accountability.
- Specialized context or procedures.
- A measurable benefit from separation.
- A runtime capable of supporting that separation.
- A verification method for the role's outputs.

A role should be merged, simplified, or removed when its responsibilities overlap excessively or it adds more coordination overhead than value.

Changes to this matrix must follow the framework's change-control process.

---

## 10. Current maturity

| Area | Status |
|---|---|
| Role definitions | Drafted |
| Responsibility boundaries | Drafted |
| Default accountability | Drafted |
| Role activation guidance | Drafted |
| Agent vs. skill recommendations | Proposed |
| Runtime implementation | Not implemented |
| Independent verification enforcement | Not implemented |
| Human approval enforcement | Not implemented |

**This document describes the proposed organizational model. It does not claim that these roles, permissions, or execution capabilities already exist.**

## 11. Next document

The next document should be:

`organization/AGENT_CATALOG.md`

It will define the actual agent inventory, including each agent's mission, activation criteria, required skills, authority, inputs, outputs, and implementation status.

The catalog will use this matrix as its source of truth rather than redefining responsibilities independently.
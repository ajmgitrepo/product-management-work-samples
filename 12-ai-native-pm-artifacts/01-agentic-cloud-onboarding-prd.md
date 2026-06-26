# Product Requirements Document: Agentic Cloud Onboarding Platform

## 1. Product Summary

The Agentic Cloud Onboarding Platform is an AI-assisted workflow that helps application teams onboard containerized applications into enterprise cloud environments across Azure and GCP. The product reduces the complexity of infrastructure onboarding by guiding teams through requirements capture, architecture recommendations, service configuration, policy checks, observability setup, deployment readiness, and production handoff.

The experience is designed around a simple natural-language request:

> “I want to onboard my application with 25 services.”

From that starting point, the platform guides the application team through required onboarding decisions, recommends the appropriate target architecture, generates structured onboarding artifacts, identifies dependencies, and routes work through human approval gates where needed.

## 2. Problem Statement

Cloud onboarding for containerized applications is often slow, fragmented, and dependent on specialized platform knowledge. Application teams may need to coordinate across multiple domains, including tenant setup, namespaces, pipelines, ingress, DNS, certificates, load balancing, API gateway configuration, WAF, observability, secrets, storage, database dependencies, and production support handoff.

This creates several recurring problems:

- App teams do not always know which information is required before onboarding can begin.
- Platform teams spend time clarifying incomplete requests and answering repetitive questions.
- Requirements, dependencies, and approval gates are distributed across documents, tickets, chats, and meetings.
- Manual coordination slows down onboarding, especially when multiple services or environments are involved.
- Production readiness is difficult to assess consistently across teams.

## 3. Target Users

### Primary User: Application Team Representative

The application team representative is responsible for getting an application onboarded to the cloud platform. They may understand the application but may not know all platform, network, security, and operational requirements.

Their goals are to understand what is required, complete onboarding quickly, avoid rework, and reach production readiness with minimal confusion.

### Secondary User: Delivery Lead

The delivery lead coordinates onboarding across the app team, platform team, engineering, network, security, and operations stakeholders.

Their goals are to reduce ambiguity, track dependencies, confirm readiness, and drive the application from initial onboarding through production handoff.

### Secondary User: Platform Engineer

The platform engineer supports configuration, provisioning, validation, and troubleshooting across cloud platform services.

Their goals are to reduce repetitive intake work, receive complete requirements, and focus on higher-value engineering tasks.

### Secondary User: Operations / CloudOps Team

The operations team supports the application after production onboarding is complete.

Their goals are to receive clean handoff documentation, understand support boundaries, and avoid production support gaps.

## 4. Current-State Workflow

A typical onboarding flow may involve the following steps:

1. App team requests onboarding.
2. Delivery lead gathers initial details.
3. App team provides buildsheet or onboarding intake information.
4. Platform team validates tenant and environment requirements.
5. Namespaces or app service boundaries are defined.
6. CI/CD or GitOps flow is configured.
7. Networking, ingress, WAF, DNS, API gateway, and load-balancer requirements are reviewed.
8. Secrets, storage, database, observability, and monitoring requirements are captured.
9. NPE validation is completed.
10. Production deployment is scheduled.
11. Production validation is completed.
12. CloudOps handoff is performed.

This process often requires repeated clarification and coordination because dependencies are not always visible upfront.

## 5. Future-State AI-Native Workflow

The AI-native workflow uses an agentic assistant to guide the application team and delivery lead through onboarding.

### Step 1: Natural-Language Intake

The app team begins with a natural-language request, such as:

> “I want to onboard my payment application with 25 services to GCP. We need external access, internal APIs, PostgreSQL, object storage, Splunk, Dynatrace, and production support handoff.”

The agent translates the request into structured onboarding requirements.

### Step 2: Guided Discovery

The agent asks targeted follow-up questions only where information is missing. Example areas include:

- Cloud target: Azure, GCP, or both
- Runtime: AKS, GKE, Cloud Run, App Service, or another target
- Number of services
- Environment needs: NPE, test, production
- External vs internal traffic
- API gateway needs
- DNS and CNAME requirements
- WAF and DDoS needs
- Secrets and certificate requirements
- Database and storage dependencies
- Observability requirements
- Support model and handoff timing

### Step 3: Architecture Recommendation

The agent recommends an onboarding pattern based on application needs. For example:

- GKE for multi-service containerized applications needing namespace-level tenancy and Kubernetes controls
- Cloud Run for simpler managed services or agent workloads that do not require cluster management
- AKS for Azure-hosted container workloads requiring Kubernetes control
- Azure App Service for web applications better suited to managed PaaS hosting
- Dedicated node pool when workload sizing, isolation, or vendor requirements exceed shared cluster defaults

### Step 4: Artifact Generation

The agent generates draft artifacts for review:

- Onboarding summary
- Buildsheet draft
- Service inventory
- Environment matrix
- Dependency list
- Network and ingress summary
- DNS and gateway checklist
- Observability checklist
- Secrets and certificate checklist
- Production readiness checklist
- Handoff summary

### Step 5: Policy and Readiness Checks

The agent checks the request against platform rules, security policies, and required onboarding gates.

Examples:

- Required fields are complete.
- Required approvals are identified.
- Runtime choice aligns with workload requirements.
- Observability requirements are included.
- Production support handoff is planned.
- High-risk changes require human approval.

### Step 6: Human Approval Gates

The agent does not independently approve high-risk or production-impacting actions. Human review is required for:

- Production deployment
- Security exceptions
- Network exposure
- Firewall or allowlist changes
- WAF policy changes
- DNS cutover
- Dedicated infrastructure allocation
- Production support transition

### Step 7: Production Handoff

Once production onboarding is complete, the agent generates a final handoff package with support links, ownership details, operational runbooks, monitoring references, and escalation paths.

## 6. Product Goals

The product should:

- Reduce onboarding time for application teams.
- Reduce repetitive clarification work for delivery leads and platform engineers.
- Improve completeness and consistency of onboarding requests.
- Increase platform self-service adoption.
- Improve production readiness and handoff quality.
- Provide a scalable operating model for onboarding multi-service applications.

## 7. Non-Goals

The initial product will not:

- Fully automate production deployment without human approval.
- Replace platform engineers, delivery leads, or operations teams.
- Make final security or architecture decisions without review.
- Support every possible runtime or cloud service on day one.
- Override enterprise governance, access control, or compliance requirements.

## 8. MVP Scope

The MVP should support guided onboarding for containerized applications targeting enterprise Azure and GCP environments.

### MVP Capabilities

- Natural-language onboarding intake
- Structured requirement extraction
- Guided follow-up questions
- Runtime recommendation logic
- Service inventory generation
- Environment matrix generation
- Dependency checklist
- Production readiness checklist
- Human approval gate identification
- Handoff summary generation

### MVP Integrations

The MVP can begin with lightweight integrations or exportable artifacts rather than full automation.

Potential integrations include:

- Jira or similar ticketing system
- GitHub or Azure DevOps repository links
- CI/CD pipeline references
- Internal platform documentation
- Observability dashboards
- Chat interface embedded in the developer portal

## 9. Future Scope

Future iterations may include:

- Direct ticket creation
- Direct pipeline template generation
- Policy-as-code validation
- Infrastructure-as-code pull request generation
- Automated documentation updates
- Integration with cloud APIs
- Deployment readiness scoring
- Cost estimation
- Drift detection
- Support ticket deflection analytics
- Multi-agent workflows for app, network, security, and operations domains

## 10. Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | User can describe an onboarding request in natural language. | Must Have |
| FR-002 | System extracts structured application, service, environment, and dependency details. | Must Have |
| FR-003 | System identifies missing required information. | Must Have |
| FR-004 | System asks targeted follow-up questions. | Must Have |
| FR-005 | System recommends a cloud/runtime onboarding pattern. | Must Have |
| FR-006 | System generates an onboarding summary. | Must Have |
| FR-007 | System generates a production readiness checklist. | Must Have |
| FR-008 | System identifies required human approval gates. | Must Have |
| FR-009 | System generates a production handoff summary. | Should Have |
| FR-010 | System integrates with ticketing or workflow tooling. | Should Have |
| FR-011 | System generates infrastructure-as-code templates or pull requests. | Could Have |
| FR-012 | System calculates onboarding readiness score. | Could Have |

## 11. Non-Functional Requirements

| Category | Requirement |
|---|---|
| Security | The system must respect role-based access controls and must not expose restricted platform data. |
| Privacy | The system must avoid including sensitive data in prompts unless approved by policy. |
| Reliability | The system must provide deterministic workflow steps where possible and clearly mark AI-generated recommendations. |
| Auditability | Key recommendations, generated artifacts, and approval steps must be logged. |
| Explainability | The system must explain why a runtime or architecture pattern was recommended. |
| Latency | Standard intake and checklist generation should complete quickly enough to feel interactive. |
| Cost | Model usage should be monitored by workflow, user, and artifact type. |
| Governance | High-risk actions must require human approval. |

## 12. Success Metrics

### Adoption Metrics

- Number of onboarding requests initiated through the AI workflow
- Percentage of app teams using AI-assisted intake
- Repeat usage by delivery leads and platform engineers

### Efficiency Metrics

- Reduction in average onboarding cycle time
- Reduction in clarification cycles per onboarding request
- Reduction in manual intake meetings
- Reduction in repetitive support tickets

### Quality Metrics

- Percentage of requests submitted with complete required fields
- Production readiness checklist completion rate
- Number of production handoff issues
- Reduction in rework caused by missing dependencies

### Trust and AI Quality Metrics

- Recommendation acceptance rate
- User feedback score
- Escalation rate to human support
- Hallucination or incorrect recommendation rate
- Percentage of outputs requiring material correction

### Business Metrics

- Increase in platform self-service adoption
- Reduction in platform support burden
- Faster time-to-production for application teams
- Improved developer satisfaction

## 13. Risks and Mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| AI provides incorrect architecture recommendation. | Poor design or rework. | Require explainability, confidence indicators, and human review. |
| App teams overtrust generated outputs. | Governance or production risk. | Clearly label AI-generated artifacts and enforce approval gates. |
| Sensitive data is included in prompts. | Security or compliance issue. | Add data handling rules, prompt filters, and access controls. |
| Workflow becomes another intake burden. | Low adoption. | Keep intake conversational and generate useful artifacts immediately. |
| Integrations are too complex for MVP. | Delayed delivery. | Start with exportable artifacts before deep system integrations. |
| Platform rules change frequently. | Outdated guidance. | Ground recommendations in maintained documentation and policy sources. |

## 14. MVP User Story Examples

### Story 1: Natural-Language Intake

As an application team representative, I want to describe my onboarding request in plain language so that I do not need to know every platform-specific intake field upfront.

**Acceptance Criteria**

- User can enter a free-form onboarding request.
- System identifies application name, number of services, cloud target, runtime, environments, and known dependencies where provided.
- System identifies missing required fields.
- System generates a structured intake summary.

### Story 2: Guided Follow-Up

As a delivery lead, I want the system to ask targeted follow-up questions so that incomplete onboarding requests can be resolved faster.

**Acceptance Criteria**

- System asks only questions relevant to missing or ambiguous fields.
- Questions are grouped by domain, such as runtime, networking, observability, and production support.
- User responses update the structured onboarding record.

### Story 3: Runtime Recommendation

As an application team representative, I want the system to recommend an appropriate hosting pattern so that I can understand whether my workload fits AKS, GKE, Cloud Run, Azure App Service, or another platform pattern.

**Acceptance Criteria**

- System provides a recommended runtime pattern.
- System explains the rationale.
- System identifies assumptions and open questions.
- System requires human review before final approval.

### Story 4: Production Readiness Checklist

As a delivery lead, I want the system to generate a production readiness checklist so that all required gates are visible before production deployment.

**Acceptance Criteria**

- Checklist includes deployment, monitoring, DNS, gateway, security, support, and validation items.
- Items are marked complete, incomplete, or needs review.
- Checklist can be exported or linked to a ticket.

## 15. Product Narrative for Interviews

This product represents an AI-native approach to enterprise platform onboarding. The goal is not to add a chatbot on top of a broken workflow. The goal is to compress a complex, multi-team onboarding journey into a guided, policy-aware experience that improves developer velocity while preserving governance.

The strongest product insight is that cloud onboarding friction is often caused by cognitive load, unclear dependencies, and fragmented ownership. An AI-native product can reduce that friction by helping users understand what is needed, generating useful artifacts, recommending next steps, and escalating high-risk decisions to humans.


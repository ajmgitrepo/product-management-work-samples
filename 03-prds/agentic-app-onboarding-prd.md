# PRD: Agentic Application Onboarding Assistant

## 1. Overview

The Agentic Application Onboarding Assistant helps application teams onboard multi-service applications into cloud-native platforms by collecting intent, mapping requirements, recommending onboarding steps, generating configuration drafts, and routing high-risk actions for approval.

Example prompt: "I want to onboard my application with 25 services."

## 2. Product Problem

Complex application onboarding requires coordination across infrastructure, Kubernetes namespaces, ingress, networking, policies, secrets, observability, CI/CD, and operational handoff. Developers often do not know which dependencies are required or in what sequence.

## 3. Product Goal

Reduce onboarding friction by turning a natural-language request into a structured onboarding plan with recommended workflows, required inputs, dependencies, and validation gates.

## 4. Target Users

- Application teams onboarding new services
- Platform engineers supporting onboarding
- Cloud operations teams receiving production handoff
- Security and compliance reviewers

## 5. Core User Journey

1. User describes the application and target environment.
2. Assistant asks for missing required details.
3. Assistant creates an onboarding plan.
4. User reviews generated configuration drafts and dependency checklist.
5. Platform workflow validates requirements.
6. Low-risk steps are prepared for execution; high-risk steps route for approval.
7. Status and blockers are tracked through completion.

## 6. MVP Capabilities

| Capability | Description |
|---|---|
| Intent capture | Convert natural language into structured onboarding requirements |
| Service inventory | Capture number of services, repos, runtime type, dependencies |
| Environment planning | Map NPE, test, and prod onboarding steps |
| Dependency checklist | Identify DNS, ingress, LB, secrets, DB, storage, monitoring, policies |
| Config draft generation | Generate draft templates for review |
| Risk classification | Flag actions requiring human approval |
| Status tracking | Show progress across onboarding stages |

## 7. Guardrails

- No autonomous production changes without explicit approval
- Human review required for DNS, ingress, traffic, security policy, and production promotion changes
- All generated configuration is draft-only until validated
- Audit log maintained for user input, generated output, approvals, and execution
- Assistant must cite internal documentation or policy sources when recommending actions

## 8. Requirements

| ID | Requirement | Priority |
|---|---|---|
| AR-001 | Accept natural-language onboarding request | P0 |
| AR-002 | Convert request into structured onboarding object | P0 |
| AR-003 | Identify missing required inputs | P0 |
| AR-004 | Produce sequenced onboarding plan | P0 |
| AR-005 | Generate draft configuration templates | P1 |
| AR-006 | Route high-risk actions for approval | P1 |
| AR-007 | Track progress and blockers | P1 |
| AR-008 | Integrate with documentation search / RAG | P1 |
| AR-009 | Capture feedback on answer quality | P2 |

## 9. Success Metrics

- Onboarding cycle time reduction
- Reduction in incomplete onboarding requests
- Support ticket deflection
- Percentage of standard onboarding steps completed via guided workflow
- User satisfaction with generated plans
- Approval rejection rate for generated drafts

## 10. Open Questions

- Which onboarding steps can be automated safely in phase one?
- Which systems become source of truth for service inventory and environment readiness?
- What approval model is required for production traffic changes?
- How should generated configuration be reviewed and versioned?
- How will hallucination risk be measured and mitigated?

## 11. Acceptance Criteria

- A user can enter a high-level onboarding request and receive a structured plan.
- The assistant identifies missing inputs before producing final configuration drafts.
- High-risk actions are clearly labeled and routed for review.
- The workflow captures status, blockers, and ownership.
- Generated output is traceable to approved templates or documentation.

# PRD: Self-Service Load Balancing as a Service

## 1. Overview

Self-Service LBaaS enables application teams to request and manage standard load balancing configurations through a governed platform workflow. The product reduces manual BAU tickets, improves configuration consistency, and accelerates application onboarding.

## 2. Goals

- Reduce routine load-balancer support tickets
- Improve request quality and completion time
- Standardize LTM/GTM patterns
- Provide visibility into health checks, DNS dependencies, and operational ownership
- Give platform teams telemetry to prioritize improvements

## 3. Non-Goals

- Replacing all enterprise load balancing platforms in the MVP
- Supporting every custom traffic pattern at launch
- Allowing unreviewed production changes for high-risk configurations

## 4. Personas

| Persona | Need |
|---|---|
| Developer | Request traffic routing without manual back-and-forth |
| Platform Engineer | Reduce repetitive support work |
| Network Engineer | Maintain guardrails and standards |
| SRE | Ensure health checks and runbooks are production-ready |

## 5. User Stories

1. As a developer, I want to submit a standard load balancing request using a guided form so that I can avoid missing required information.
2. As a platform engineer, I want requests validated before submission so that I receive fewer incomplete tickets.
3. As a network engineer, I want risky changes routed for approval so that production traffic remains protected.
4. As an SRE, I want health check and monitoring requirements captured so that operational readiness is clear.
5. As a product manager, I want usage and cycle-time metrics so that roadmap decisions are based on evidence.

## 6. Functional Requirements

| ID | Requirement | Priority |
|---|---|---|
| FR-001 | Guided intake for standard LTM/GTM requests | P0 |
| FR-002 | Required field validation before submission | P0 |
| FR-003 | Environment selection: NPE, test, prod | P0 |
| FR-004 | Health check configuration capture | P0 |
| FR-005 | DNS / CNAME dependency visibility | P1 |
| FR-006 | Approval routing for high-risk production changes | P1 |
| FR-007 | Request status tracking | P1 |
| FR-008 | Audit log for submitted and approved changes | P1 |
| FR-009 | Dashboard metrics for adoption, cycle time, and failures | P1 |

## 7. Non-Functional Requirements

- Secure by default
- Auditable request history
- Role-aware access controls
- Clear rollback procedure
- Compatible with existing enterprise load balancing patterns
- Observable workflow health and request outcomes

## 8. MVP Scope

### Included
- Standard traffic request pattern
- Basic validation
- Health check details
- Environment-aware workflow
- Manual approval gate where required
- Metrics capture

### Deferred
- Fully automated execution for all request types
- Advanced traffic steering policies
- Multi-cloud parity for every LB pattern
- AI recommendation engine for traffic configuration

## 9. Success Metrics

| Metric | Baseline | MVP Target |
|---|---:|---:|
| Routine LB support tickets | Current ticket volume | 40–60% reduction |
| Request cycle time | Current median | 30–50% reduction |
| Incomplete requests | Current percentage | 50% reduction |
| Self-service adoption | New metric | 70% of standard requests |
| Request failure rate | New metric | Downward trend |

## 10. Risks

| Risk | Mitigation |
|---|---|
| Incorrect traffic configuration | Validation, approvals, audit logs, rollback |
| Low adoption | Training, templates, support champions |
| Edge cases overwhelm MVP | Start with standard patterns, track exceptions |
| Operational ownership unclear | Require ownership and runbook fields |

## 11. Acceptance Criteria

- A developer can submit a complete standard LB request without opening a manual support ticket.
- Required fields prevent incomplete submissions.
- High-risk changes are routed for review.
- The platform captures status and key workflow timestamps.
- Product and platform teams can view adoption and cycle-time metrics.

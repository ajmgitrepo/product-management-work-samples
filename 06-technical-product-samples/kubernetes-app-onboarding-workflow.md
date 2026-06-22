# Kubernetes Application Onboarding Workflow

## Purpose

Translate a complex technical onboarding process into a clear product workflow for application teams, platform engineers, security, networking, and operations.

## Scenario

An application team needs to onboard a multi-service application into a shared Kubernetes platform. The platform already has clusters and namespaces available, but new workloads, ingress patterns, policies, observability, and operational handoff must be configured.

## Workflow Stages

### 1. Intake and Scoping
- Application name
- Business owner
- Technical owner
- Target environment
- Number of services
- Runtime type
- External/internal exposure requirements
- Data dependencies
- Compliance classification

### 2. Platform Readiness
- Confirm tenant or landing zone
- Confirm cluster and namespace model
- Validate resource quotas
- Confirm node pool requirements
- Confirm service account and secrets approach

### 3. Deployment Readiness
- Image repository confirmed
- CI/CD pipeline created or updated
- Helm/Kustomize manifests reviewed
- Environment variables and secrets defined
- Rollback approach documented

### 4. Network and Traffic Readiness
- Ingress requirements captured
- DNS / CNAME requirements captured
- Load balancer pattern selected
- Health checks defined
- WAF or gateway dependencies identified
- Internal/external exposure validated

### 5. Security and Policy Readiness
- Network policies reviewed
- mTLS/service mesh requirements confirmed
- Secrets management validated
- Required approvals completed
- Audit and compliance requirements captured

### 6. Observability and Operations
- Metrics endpoint configured
- Logs routed
- Traces configured where applicable
- Dashboards created
- Alerts configured
- Runbook documented
- Support ownership confirmed

### 7. Environment Promotion
- NPE validation complete
- Test validation complete
- Production readiness review complete
- Production deployment complete
- CloudOps / SRE handoff complete

## Product Manager Value

A technical PM should not need to personally execute every infrastructure task, but should be able to identify dependencies, sequence work, clarify ownership, define acceptance criteria, and reduce ambiguity for cross-functional teams.

## Acceptance Criteria Example

- Namespace exists and is assigned to the correct tenant/application.
- Application workloads deploy successfully in NPE.
- Required ingress and traffic routing are validated.
- Health checks pass.
- Observability dashboards and alerts are live.
- Runbook and ownership are documented.
- Production handoff is accepted by operations.

# Developer Onboarding Discovery Brief

## Discovery Objective

Understand why application onboarding into container platforms takes longer than expected and identify opportunities to reduce friction, standardize workflows, and improve developer confidence.

## Research Inputs

- Interviews with application teams
- Platform support ticket themes
- Onboarding documentation review
- Workflow observation across intake, provisioning, deployment, and validation
- Feedback from platform engineering and operations teams

## Key Personas

### Application Developer
Needs to deploy services quickly without becoming an infrastructure expert.

### Application Architect
Needs confidence that routing, security, scaling, observability, and deployment patterns meet enterprise standards.

### Platform Engineer
Needs consistent intake and fewer repeat questions from app teams.

### Operations / SRE
Needs clear handoff, ownership, monitoring, and runbook readiness.

## Jobs To Be Done

- When I need to onboard a new application, I want a clear golden path so I can understand requirements and avoid rework.
- When I deploy a service, I want standard patterns for ingress, DNS, load balancing, and observability so I can move faster with fewer support dependencies.
- When I run into an issue, I want contextual guidance so I can self-resolve common blockers.
- When I hand off to operations, I want evidence that health checks, monitoring, and runbooks are complete.

## Pain Points

| Pain Point | Impact |
|---|---|
| Unclear prerequisites | Rework and delays |
| Manual cross-team handoffs | Slow cycle time |
| Inconsistent request quality | Support burden |
| Fragmented documentation | Developer frustration |
| Late discovery of networking/security gaps | Release risk |
| Poor telemetry | Weak prioritization signals |

## Opportunity Areas

1. Create a single onboarding checklist organized by environment and dependency.
2. Provide reusable templates for common service patterns.
3. Integrate policy, ingress, load balancing, DNS, and health checks into one workflow view.
4. Add AI-assisted documentation and troubleshooting guidance.
5. Build telemetry dashboards to track onboarding progress and blockers.

## Problem Statement

Application teams need a predictable and self-service onboarding experience because current workflows rely on fragmented documentation, manual coordination, and unclear dependency ownership, resulting in avoidable delays and support tickets.

## MVP Recommendation

Start with a guided onboarding workflow for standard Kubernetes services that includes prerequisites, namespace setup, deployment checklist, ingress/load balancing steps, health validation, monitoring requirements, and support escalation paths.

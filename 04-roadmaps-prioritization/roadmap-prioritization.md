# Roadmap and Prioritization Sample

## Product Area

Internal Developer Platform for cloud-native application onboarding and platform self-service.

## Roadmap Themes

1. Developer onboarding acceleration
2. Self-service infrastructure workflows
3. Operational visibility and reliability
4. AI-assisted support and troubleshooting
5. Governance, security, and compliance by design

## Prioritization Framework

Prioritization uses a blended RICE + risk/dependency model.

| Factor | Definition |
|---|---|
| Reach | Number of teams, services, or workflows impacted |
| Impact | Expected improvement in speed, reliability, cost, or support volume |
| Confidence | Evidence strength from tickets, interviews, telemetry, or incidents |
| Effort | Engineering, platform, security, and operational complexity |
| Risk | Production, security, compliance, or migration risk |
| Dependency | Required sequencing across teams or platforms |

## Example Prioritized Backlog

| Initiative | Reach | Impact | Confidence | Effort | Priority | Rationale |
|---|---:|---:|---:|---:|---|---|
| Guided onboarding checklist | High | High | High | Medium | P0 | Addresses broad onboarding friction |
| Self-service LBaaS standard requests | High | High | High | Medium | P0 | Reduces high-volume support tickets |
| Platform telemetry dashboard | Medium | High | High | Medium | P0 | Enables product health and prioritization |
| AI-assisted support in portal | Medium | Medium | Medium | Medium | P1 | Deflects common support questions |
| Advanced traffic policy automation | Medium | High | Low | High | P2 | Valuable but higher risk and complexity |
| Multi-cloud parity for all workflows | Medium | Medium | Medium | High | P2 | Important, but dependency-heavy |

## Quarter-Level Roadmap

### Q1: Standardize
- Launch onboarding checklist
- Define golden path templates
- Capture baseline onboarding and support metrics
- Create readiness criteria for NPE/test/prod

### Q2: Self-Service
- Launch standard LBaaS request workflow
- Add validation and request tracking
- Publish team enablement content
- Start platform health dashboard

### Q3: Scale
- Expand supported app patterns
- Integrate AI-assisted support
- Add deeper observability and incident correlation
- Improve approval workflow and auditability

### Q4: Optimize
- Automate additional low-risk workflows
- Improve multi-cloud parity
- Use telemetry to reduce top friction points
- Expand executive dashboard and adoption reporting

## Tradeoff Example

A team requested advanced traffic steering automation before MVP launch. The request had high potential value but required deeper network engineering review, stronger rollback controls, and more production risk analysis. The decision was to defer it to P2 and prioritize standard request automation first because it addressed the largest ticket volume with lower implementation risk.

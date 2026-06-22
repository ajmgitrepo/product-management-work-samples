# Platform Metrics Dashboard Specification

## Objective

Create a product health dashboard that shows whether the internal developer platform is improving onboarding speed, adoption, reliability, and support efficiency.

## Dashboard Users

- Product leadership
- Platform engineering managers
- SRE / operations leaders
- Developer experience teams
- Executive stakeholders

## KPI Categories

### Adoption
| Metric | Definition |
|---|---|
| Active users | Unique users completing platform workflows |
| Onboarded services | Services onboarded through the platform |
| Self-service completion rate | % of eligible requests completed without manual ticketing |
| Repeat usage | Teams using platform workflows more than once |

### Speed
| Metric | Definition |
|---|---|
| Median onboarding cycle time | Time from request start to environment readiness |
| Request completion time | Time from submitted request to completion |
| Blocker aging | Time spent waiting on dependency resolution |
| Environment promotion time | Time from NPE readiness to production promotion |

### Quality and Reliability
| Metric | Definition |
|---|---|
| Failed workflow rate | % of workflows failing validation or execution |
| Incident correlation | Incidents linked to onboarding/configuration issues |
| Health check readiness | % of services with valid health checks before prod |
| Monitoring readiness | % of services with required observability configured |

### Support Efficiency
| Metric | Definition |
|---|---|
| BAU ticket volume | Routine support tickets by category |
| Ticket deflection | Estimated tickets avoided through self-service |
| AI support resolution | % of support questions resolved by assistant |
| Escalation rate | % of workflows requiring platform intervention |

## Example Executive View

| KPI | Status | Trend | Product Interpretation |
|---|---|---|---|
| Onboarding cycle time | Improving | Down | Golden path is reducing friction |
| Self-service adoption | Improving | Up | Developers are shifting from tickets to platform workflows |
| BAU tickets | Improving | Down | Automation is reducing manual demand |
| Failed workflows | Watch | Flat | Validation gaps may require backlog attention |
| Developer CSAT | Improving | Up | Enablement and UX are helping adoption |

## Instrumentation Events

- onboarding_started
- prerequisite_completed
- validation_failed
- request_submitted
- approval_required
- approval_completed
- workflow_completed
- support_article_opened
- ai_assistant_used
- ticket_escalated

## Product Decisions Enabled

- Which workflows should be automated next
- Which onboarding steps create the most delay
- Which teams need enablement
- Which platform areas generate the most support burden
- Whether AI-assisted support is reducing tickets or creating confusion

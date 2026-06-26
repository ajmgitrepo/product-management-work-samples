# AI Product Evaluation Framework

## 1. Purpose

This framework helps product teams evaluate AI features beyond novelty. It is designed for enterprise products where trust, governance, reliability, and measurable outcomes matter as much as user experience.

The framework can be used for:

- AI copilots
- AI assistants
- Agentic workflows
- AI-powered support tools
- AI-generated recommendations
- RAG-based knowledge experiences
- Workflow automation features
- Internal productivity tools

## 2. Core Principle

AI features should not be judged only by whether they work in a demo. They should be judged by whether they create measurable value, reduce user friction, improve decision quality, and operate safely within business constraints.

A useful AI product should answer four questions:

1. Does it solve a real user problem?
2. Does it perform reliably enough for the workflow?
3. Does the user trust it?
4. Does it create measurable business value?

## 3. Evaluation Dimensions

### Dimension 1: User Value

This dimension evaluates whether the AI capability solves a meaningful problem.

| Criteria | Evaluation Question |
|---|---|
| Problem relevance | Is the AI feature tied to a real user pain point? |
| Workflow fit | Does it improve an existing workflow rather than create extra work? |
| Time savings | Does it reduce time spent on repetitive or complex tasks? |
| Cognitive load reduction | Does it help users understand, decide, or act faster? |
| User satisfaction | Do users report that the AI output is useful and easy to apply? |

### Scoring Guide

| Score | Meaning |
|---|---|
| 1 | Novelty feature with unclear user value |
| 2 | Some user value, but weak workflow fit |
| 3 | Clear value for a defined use case |
| 4 | Strong value with measurable workflow improvement |
| 5 | High-value capability that changes how users work |

## 4. Business Impact

This dimension evaluates measurable business outcomes.

| Criteria | Evaluation Question |
|---|---|
| Adoption | Are target users actively using the feature? |
| Efficiency | Does it reduce cycle time, support load, or manual effort? |
| Revenue impact | Does it improve conversion, retention, expansion, or monetization? |
| Cost reduction | Does it reduce operational burden or support costs? |
| Strategic fit | Does it strengthen the product’s competitive position? |

### Example Metrics

- Support ticket deflection rate
- Onboarding cycle time reduction
- Feature adoption rate
- Active usage by target persona
- Customer satisfaction or NPS movement
- Retention or expansion influence
- Manual work avoided
- Cost per successful AI interaction

## 5. AI Quality

This dimension evaluates the actual quality of AI outputs.

| Criteria | Evaluation Question |
|---|---|
| Accuracy | Is the output factually and contextually correct? |
| Completeness | Does it include the information needed for the task? |
| Relevance | Is the output specific to the user’s intent and context? |
| Consistency | Does it produce stable results for similar inputs? |
| Explainability | Can the system explain its recommendation or reasoning at a useful level? |
| Grounding | Is the output based on trusted sources or enterprise knowledge? |

### Example Metrics

- Correct answer rate
- Hallucination rate
- Human correction rate
- Recommendation acceptance rate
- Output completeness score
- Grounded-source coverage
- Regression test pass rate

## 6. User Trust

This dimension evaluates whether users understand and trust the AI experience.

| Criteria | Evaluation Question |
|---|---|
| Transparency | Does the user know when content is AI-generated? |
| Confidence signaling | Does the system show uncertainty when appropriate? |
| Human control | Can users review, edit, approve, or reject AI outputs? |
| Escalation | Can the user easily escalate to a human or expert workflow? |
| Feedback loop | Can users rate, correct, or comment on the output? |

### Example Metrics

- Upvote/downvote rate
- User correction rate
- Escalation rate
- Trust score from user surveys
- Percentage of outputs accepted without change
- Repeat usage rate

## 7. Operational Readiness

This dimension evaluates whether the AI feature can operate reliably in production.

| Criteria | Evaluation Question |
|---|---|
| Latency | Is response time acceptable for the workflow? |
| Availability | Is the service reliable enough for user needs? |
| Monitoring | Are usage, failures, latency, cost, and quality monitored? |
| Fallbacks | Does the system handle failure gracefully? |
| Supportability | Can support and engineering teams troubleshoot issues? |
| Version control | Are prompts, models, retrieval sources, and workflows tracked? |

### Example Metrics

- Average and p95 response latency
- Error rate
- Fallback rate
- Model timeout rate
- Cost per session
- Retrieval failure rate
- Incident count

## 8. Governance and Risk

This dimension evaluates enterprise-readiness.

| Criteria | Evaluation Question |
|---|---|
| Data privacy | Does the system protect sensitive or regulated information? |
| Access control | Does output respect user permissions? |
| Auditability | Are important actions and recommendations logged? |
| Policy alignment | Does the feature comply with internal governance? |
| Risk tiering | Are high-risk use cases subject to stricter controls? |
| Human approval | Are critical actions gated by humans? |

### Example Metrics

- Policy violation rate
- Unauthorized data exposure incidents
- Audit log completeness
- Number of blocked unsafe requests
- Human approval compliance rate
- Risk review completion rate

## 9. Cost and Scalability

This dimension evaluates whether the AI product can scale sustainably.

| Criteria | Evaluation Question |
|---|---|
| Unit economics | Is the cost per interaction acceptable? |
| Model selection | Is the model appropriate for the task complexity? |
| Token efficiency | Are prompts and context windows optimized? |
| Caching | Can repeated work be reduced? |
| Scalability | Can the system support expected growth? |
| Cost visibility | Can product and engineering teams see cost by workflow? |

### Example Metrics

- Cost per user session
- Cost per successful task
- Token usage by workflow
- Cache hit rate
- Usage by model type
- Marginal cost per additional user

## 10. AI Product Scorecard

Use this scorecard to compare AI feature candidates or evaluate a feature before launch.

| Dimension | Weight | Score 1–5 | Weighted Score |
|---|---:|---:|---:|
| User Value | 25% |  |  |
| Business Impact | 20% |  |  |
| AI Quality | 20% |  |  |
| User Trust | 15% |  |  |
| Operational Readiness | 10% |  |  |
| Governance and Risk | 5% |  |  |
| Cost and Scalability | 5% |  |  |
| **Total** | **100%** |  |  |

## 11. Launch Readiness Checklist

Before launching an AI feature, confirm:

- The target user and workflow are clearly defined.
- The AI feature solves a meaningful problem.
- Success metrics are defined before launch.
- AI outputs are tested against realistic scenarios.
- Known failure modes are documented.
- Users can provide feedback.
- High-risk actions require human approval.
- Monitoring is in place for usage, quality, latency, and cost.
- Support teams know how to handle escalations.
- Governance, privacy, and access controls have been reviewed.

## 12. Example Application: AI-Assisted Developer Platform Support

### Use Case

An embedded GenAI support assistant helps developers troubleshoot onboarding and platform questions inside a developer portal.

### Primary User Problem

Developers struggle to find the right documentation, understand onboarding steps, and resolve common platform issues without opening support tickets.

### Success Metrics

| Category | Example Metric |
|---|---|
| Adoption | Percentage of platform users engaging with the assistant |
| Efficiency | Reduction in repetitive support tickets |
| Quality | Correct answer rate and human correction rate |
| Trust | Upvote/downvote ratio and repeat usage |
| Operations | Escalation rate and response latency |
| Business | Reduced support burden and faster onboarding |

### Evaluation Summary

A strong AI support assistant should not simply answer questions. It should guide users to the next best action, cite trusted platform knowledge, identify uncertainty, and route complex issues to the right support path.

## 13. Example Application: Agentic Cloud Onboarding

### Use Case

An AI-assisted agent helps an app team onboard a multi-service application to Azure or GCP.

### Primary User Problem

Application teams do not always understand the full set of infrastructure, network, security, observability, and production readiness requirements.

### Success Metrics

| Category | Example Metric |
|---|---|
| Adoption | Number of onboarding requests started through AI intake |
| Efficiency | Reduction in onboarding cycle time |
| Quality | Increase in complete intake submissions |
| Trust | Recommendation acceptance rate |
| Governance | Human approval compliance for high-risk changes |
| Business | Faster time-to-production and reduced platform support load |

### Evaluation Summary

The agent should be evaluated on whether it reduces onboarding friction while preserving enterprise control. The product succeeds only if it helps teams move faster without increasing production, security, or compliance risk.

## 14. Interview Narrative

A practical way to explain this framework in an interview:

> I evaluate AI products across value, quality, trust, operations, governance, and cost. I don’t treat AI as successful because it generates a plausible answer. I want to know whether it improves a real workflow, whether users trust it, whether the output is accurate enough for the use case, whether it has the right human approval gates, and whether the business impact is measurable.

For enterprise platforms, that means AI should reduce complexity, improve self-service, and accelerate delivery while still respecting security, access control, auditability, and production readiness.


# DORA Capability Reference Guide

The DevOps Research and Assessment (DORA) is a long-running, academically rigorous research program that uses behavioral science to connect software delivery methods to organizational goals and personal well-being. DORA has identified a set of capabilities proven to drive software delivery and organizational performance. This guide covers all current DORA capabilities, grouped into three categories: **AI**, **Core**, and **Secondary**.

## Before Reading

This guide is a snapshot of the capabilities documented at [dora.dev](https://dora.dev/) and is intended as a working reference for consultants advising clients on DORA adoption. Each entry provides a summary of key takeaways, measurement guidance, connections to the DORA key metrics, cost savings implications, and related capabilities. For the most current detail, follow the source link at the end of each section.

---

## DORA Key Metrics

All capabilities feed into DORA's four software delivery performance metrics — often called "the four keys." These metrics are leading indicators of organizational performance and lagging indicators of delivery practices. They apply at the application or service level, not across entire organizations. The best use of these metrics is to track the same application over time, not to compare across different teams or contexts.

- **Change Lead Time** — Time from code commit to production deployment. Measures throughput efficiency. *2025 benchmarks: 9.4% of teams achieve under 1 hour; 15% achieve 1 hour–1 day; 31.9% achieve 1 day–1 week; 26.6% achieve 1 week–1 month; 17.2% achieve over 1 month.*
- **Deployment Frequency** — How often the team deploys to production. Measures ability to deliver value continuously. *2025 benchmarks: 16.2% deploy on demand; 26.2% deploy multiple times per day; 18.7% deploy once per day; 17.6% deploy multiple times per week.*
- **Failed Deployment Recovery Time** — Time to recover from a failed deployment. Evolved from the earlier "Mean Time to Restore." Measures resilience. *2025 benchmarks: 26.8% recover in under 1 hour; 38.3% recover in 1–24 hours.*
- **Change Fail Rate** — The percentage of deployments that require immediate intervention. Measures delivery stability. *2025 benchmarks: 9.9% report a 0% failure rate; 19.9% report a 1–5% failure rate.*

DORA research confirms that speed and stability are *not* trade-offs: top performers excel across all four metrics simultaneously. Teams concerned about AI adoption should note that the 2025 DORA report found AI currently improves throughput metrics but also tends to increase instability — making the stability metrics especially important to monitor during AI adoption.

To measure where you stand, take the [DORA Quick Check](https://dora.dev/quickcheck/).

---

## AI Capabilities

The AI capabilities emerged from DORA's 2025 research and represent the organizational and technical practices that determine whether AI adoption drives real performance improvement. DORA's central finding is that **AI is an amplifier** — it magnifies existing strengths but also existing dysfunctions. Teams that lack the following capabilities are likely to find that AI accelerates problems rather than resolves them. These capabilities also directly moderate whether AI investments translate into organizational performance or remain localized productivity gains.

---

### AI-Accessible Internal Data

AI-accessible internal data securely connects AI systems to an organization's proprietary information — codebases, documentation, operational metrics, style guides — to provide context-aware responses. This moves AI tools from generic coding assistants into specialized experts that understand your specific architecture, business logic, and standards. The discipline required to make this work is called *context engineering*: rather than just writing a prompt, teams build systems that automatically gather and structure the most relevant internal context for any given AI request.

#### Key Takeaways

- AI tools connected to relevant internal data produce higher-quality, more trustworthy outputs because the AI has the context needed to apply your team's specific standards.
- Without this capability, AI operates generically, potentially reinforcing outdated patterns or introducing hallucinations.
- Context engineering — managing what information the AI is given — is more impactful than prompt engineering alone.
- Access controls matter: always implement least-privilege access so AI retrieves data using the requesting user's own credentials.
- Start small: pilot with a single, high-value data source (like one service's API documentation) before scaling.
- Documentation quality is a prerequisite: AI can only use internal data if that data is well-organized and current. DORA research shows that improving documentation quality multiplies the effectiveness of other capabilities like CI (34% → 750% improvement) and continuous delivery (63% → 656% improvement).

#### How to Measure

- Developer experience survey: "When I use AI tools, they understand our codebase and coding standards" (1–7 scale)
- % of AI-generated code suggestions accepted without modification (proxy for relevance)
- Number of internal data sources connected to AI tooling
- Time-to-useful-response for AI-assisted code lookup tasks (before/after integration)

#### DORA Metrics Impact

Strong AI-accessible internal data primarily improves **Change Lead Time** and **Deployment Frequency** by reducing the time developers spend searching for context. DORA's 2025 empirical data show this capability positively moderates AI's impact on product performance. Without it, AI's throughput gains may be offset by increased **Change Fail Rate** from context-blind suggestions.

#### Cost Savings Connection

DORA research identifies three sources of ROI from improved software delivery: (1) value from unnecessary rework avoided, (2) potential value from reinvestment in new features, and (3) cost of downtime avoided. AI-accessible internal data targets all three: it reduces rework by keeping AI suggestions aligned with existing architecture; it enables more ambitious feature work; and it shortens the feedback loop when incidents occur. Because only about one-third of features in a mature product deliver top-line value, anything that helps teams build the right things — which is what contextual AI enables — directly improves return on investment.

#### Related Capabilities

- Documentation Quality
- Version Control
- AI-Accessible Internal Platform
- Healthy Data Ecosystems

**Source:** [AI-Accessible Internal Data](https://dora.dev/capabilities/ai-accessible-internal-data/)

---

### Clear AI Stance

A clear AI stance is an organization's explicit, shared position on how, when, and why AI tools should (and should not) be used in software delivery. It covers permitted tools, data governance rules, acceptable use cases, cost guidelines, and escalation paths. Without it, teams either avoid AI out of uncertainty or adopt it inconsistently, creating compliance risks and uneven performance.

#### Key Takeaways

- Clarity is an enabler: teams with clear guidelines experiment more confidently than teams left to guess at boundaries.
- Guidelines must address cost, data privacy, security, and acceptable use — all four dimensions shape day-to-day decisions.
- This is a leadership responsibility, not just a policy document: leaders must visibly model the stance and update it as the AI landscape evolves.
- A "trust but verify" mindset should be embedded in the stance — 30% of practitioners in the 2025 DORA survey reported little or no trust in AI-generated code, and guidelines should acknowledge this rather than assume blind adoption.
- The stance must balance the freedom to experiment with the constraints that govern tool choice (cost, compliance, architecture).
- Concern about AI dependency (skill atrophy, "vibe coding," cognitive debt) is legitimate and healthy; the stance should create structured ways for teams to preserve foundational skills while benefiting from AI.

#### How to Measure

- Developer experience survey: "I understand what AI tools I am and am not allowed to use" and "I understand the policies for how I should use AI" (1–7 scale)
- % of developers who have received AI use training or onboarding
- Time from new AI tool emergence to organizational guidance publication
- Incident rate from non-approved AI tool usage

#### DORA Metrics Impact

Clear AI stance enables more consistent AI adoption, which the 2025 DORA data correlates with throughput improvements (**Change Lead Time** and **Deployment Frequency**). Without clarity, teams face friction that slows velocity. Teams with an unclear stance also tend to skip validation of AI-generated code, elevating **Change Fail Rate**.

#### Cost Savings Connection

Unclear AI policies expose organizations to compliance risk, shadow IT costs, and uneven productivity. When team members spend time guessing at acceptable use rather than delivering value, that time shows up directly in DORA's rework formula: Staff × Salary × Benefits × % time on unnecessary rework. A clear stance eliminates a significant category of rework — the rework that results from AI-generated code that violated undocumented constraints and had to be rewritten. Organizations with 250+ technical staff can expect annual rework costs in the hundreds of thousands to millions of dollars; AI policies that prevent one class of rework contribute meaningfully to that number.

#### Related Capabilities

- Transformational Leadership
- Learning Culture
- Healthy Data Ecosystems

**Source:** [Clear AI Stance](https://dora.dev/capabilities/clear-ai-stance/)

---

### Healthy Data Ecosystems

A healthy data ecosystem is the combination of data quality, accessibility, governance, and infrastructure that allows AI tools, teams, and processes to function effectively. This capability describes the underlying data health that makes all other AI capabilities possible: without clean, trustworthy, accessible data, AI tools produce unreliable outputs regardless of how well configured they are.

#### Key Takeaways

- Data quality problems upstream become AI output problems downstream — AI amplifies both the signal and the noise in your data.
- Governance is the foundation: data ownership, access controls, retention policies, and quality standards must be defined before connecting data to AI.
- This capability supports not just AI but also observability, incident response, and capacity planning — the benefits are organization-wide.
- Documentation quality directly determines the health of the human-generated data that AI depends on for code context, onboarding, and architecture understanding.
- DORA's 2025 research found that healthy data ecosystems are among the strongest predictors of AI having a positive (rather than neutral or negative) impact on product performance.

#### How to Measure

- % of production data pipelines with defined ownership and SLAs
- Data quality score (completeness, accuracy, freshness) for AI-consumed data sources
- Mean time to resolve data quality incidents
- Developer experience survey: "The data and metrics available to me are trustworthy and help me make good decisions" (1–7 scale)

#### DORA Metrics Impact

Healthy data ecosystems most directly improve **Failed Deployment Recovery Time** by ensuring observability data is accurate and actionable during incidents. They also indirectly support **Change Lead Time** by providing reliable feedback loops. Poor data health elevates **Change Fail Rate** because teams make deployment decisions based on incomplete or inaccurate signals.

#### Cost Savings Connection

DORA's ROI framework highlights downtime cost as a major value driver. The formula for avoiding downtime depends on fast detection and recovery — both of which require healthy data. Organizations that invest in data ecosystems reduce the duration of incidents, which directly reduces the per-incident cost. Additionally, reliable data prevents a category of expensive rework caused by acting on incorrect signals: deploying a fix based on bad monitoring data, then needing another fix when the root cause turns out to be different.

#### Related Capabilities

- Monitoring and Observability
- AI-Accessible Internal Data
- Documentation Quality
- Version Control

**Source:** [Healthy Data Ecosystems](https://dora.dev/capabilities/healthy-data-ecosystems/)

---

### Quality Internal Platforms

A quality internal platform is a curated, developer-facing layer of tools, services, and infrastructure that reduces cognitive load by abstracting away complex decisions. High-quality platforms let developers deploy, test, monitor, and debug without deep expertise in the underlying infrastructure. This is the organizational substrate that determines whether AI investment reaches the team level or gets absorbed by system friction.

#### Key Takeaways

- Platform quality is the single biggest determinant of whether individual AI productivity gains translate into team-level and organizational performance improvements.
- Without a quality platform, AI accelerates individual code generation while downstream bottlenecks (slow CI, manual deployments, complex environments) absorb the throughput gains — DORA calls this "downstream chaos."
- Value Stream Mapping (VSM) is the recommended tool for identifying where platform gaps are absorbing AI productivity: map the full delivery flow, identify the actual system-level constraint, and apply AI to clearing that specific bottleneck.
- Developer experience is the right lens: platforms should be designed like products, with internal users who have preferences and frustrations that need to be surfaced regularly.
- The 2025 DORA data show that quality internal platforms are among the strongest positive moderators of AI impact on software delivery performance.

#### How to Measure

- Developer experience survey: "I have the tools and infrastructure I need to do my work effectively" (1–7 scale)
- SPACE metrics for developer experience (Satisfaction, Performance, Activity, Communication, Efficiency)
- Deployment lead time from developer commit to production (platform-contributed wait times)
- % of developer-facing tickets that are platform friction vs. product issues

#### DORA Metrics Impact

Quality internal platforms directly improve all four DORA metrics. Deployment automation improves **Deployment Frequency** and **Change Lead Time**. Reliable environments improve **Change Fail Rate**. Fast rollback tooling reduces **Failed Deployment Recovery Time**. When combined with AI, strong platforms ensure those improvements compound rather than cancel out.

#### Cost Savings Connection

DORA's ROI framework identifies reinvestment value as a key source of savings: time freed from low-value work can be redirected to new features. A quality platform removes a major category of low-value work — the toil of configuring environments, navigating complex deployment pipelines, and debugging infrastructure. The 2025 DORA data show that teams with strong platforms are far more likely to convert AI productivity gains into organizational performance. Given that only about one-third of features in a mature product deliver top-line value, enabling teams to ship the right features faster rather than fighting infrastructure has a disproportionate financial impact.

#### Related Capabilities

- Deployment Automation
- Continuous Integration
- Continuous Delivery
- Monitoring and Observability

**Source:** [Quality Internal Platforms](https://dora.dev/capabilities/quality-internal-platforms/)

---

### Strong Version Control

Strong version control is the disciplined, organization-wide practice of using version control systems as the source of truth for all code, configuration, and infrastructure changes — with frequent commits, well-structured history, and automated rollback capabilities. In the context of AI, version control takes on an additional function: it serves as the "psychological safety net" that makes it safe to accept AI-generated suggestions, because any mistake can be quickly traced and reverted.

#### Key Takeaways

- Frequent commits are a leading predictor of AI having a positive (vs. neutral) impact on software delivery — the 2025 DORA data show commit frequency as a moderating variable.
- Rollback capability moderates AI's stability impact: teams with strong rollback practices see less elevation in **Change Fail Rate** when using AI.
- Version control is the foundation for all other delivery capabilities: CI, CD, trunk-based development, and deployment automation all depend on it.
- "Strong" version control is not just having Git — it includes well-structured branching, small commits, meaningful commit messages, and automated testing that provides confidence in each commit.
- Infrastructure-as-code and configuration-as-code should be treated with the same version control discipline as application code.

#### How to Measure

- Average commit frequency per developer per day
- % of infrastructure and configuration changes tracked in version control
- Time to identify the exact commit that introduced a production incident
- % of deployments with documented, tested rollback procedures

#### DORA Metrics Impact

Strong version control improves **Change Lead Time** through smaller, more reviewable change sets. It improves **Failed Deployment Recovery Time** by enabling fast rollbacks. It reduces **Change Fail Rate** by creating clear change history that makes root cause analysis faster and more accurate. The 2025 DORA data confirm that rollback capability specifically moderates AI's tendency to increase instability.

#### Cost Savings Connection

Version control's ROI is most visible in incident response. The DORA ROI framework identifies downtime cost as a key value lever — and fast rollback directly reduces downtime duration. Beyond incidents, strong version control reduces the cost of rework by making it easy to identify exactly when and why a regression was introduced, enabling targeted fixes rather than broad rewrites. In AI-accelerated development, where code is generated faster and reviewed less carefully, version control becomes the safety net that prevents expensive cascading failures.

#### Related Capabilities

- Continuous Integration
- Trunk-Based Development
- Deployment Automation
- Continuous Delivery

**Source:** [Version Control](https://dora.dev/capabilities/version-control/)

---

## Core Capabilities

The core capabilities are the technical and organizational practices with the strongest, most consistently replicated evidence of impact on software delivery performance and organizational outcomes. These are the foundational investments for any team looking to improve.

---

### Code Maintainability

Code maintainability is the degree to which a codebase can be efficiently understood, modified, tested, and extended by any team member. It encompasses code structure, naming clarity, test coverage, and the systematic elimination of technical debt. DORA research identifies maintainability as a strong predictor of both team well-being and delivery performance.

#### Key Takeaways

- High-quality, maintainable code directly reduces the cognitive load required to make changes safely, which compresses change lead time.
- Technical debt is a compounding tax on delivery speed: every new feature added to an unmaintainable codebase costs more than the last.
- DORA research shows code maintainability is strongly associated with reduced burnout — developers working in clean, well-tested codebases report significantly higher job satisfaction.
- Refactoring should be treated as part of normal delivery work, not as a separate project that competes with feature delivery.
- Generative AI can accelerate both the creation of documentation for existing code and the generation of test scaffolding — but only if the team maintains the discipline to review, validate, and own AI-generated contributions.
- The "trust but verify" mindset applies here: 30% of practitioners in the 2025 DORA survey reported little or no trust in AI-generated code, making human review a non-negotiable practice.

#### How to Measure

- Developer experience survey: "It is easy for me to find and update the relevant code within the codebase" (1–7 scale)
- Code quality metrics: cyclomatic complexity, code coverage, duplication percentage
- Time to onboard a new developer to first production-ready contribution
- % of changes requiring refactoring before implementation

#### DORA Metrics Impact

Maintainable code reduces **Change Lead Time** by removing the friction of understanding complex code before making changes. It reduces **Change Fail Rate** by making the impact of changes more predictable. Teams with high maintainability spend less time on unplanned recovery work, which improves all four metrics over time.

#### Cost Savings Connection

Code maintainability is one of the most direct levers on rework cost. DORA's rework formula (Technical Staff Size × Average Salary × Benefits Multiplier × % time on unnecessary rework) is largely driven by time spent untangling complex code. High performers spend significantly less time on rework than low performers. Improving maintainability also increases the reinvestment value of each hour saved: developers who aren't fighting the codebase have more capacity to ship the features that drive revenue.

#### Related Capabilities

- Documentation Quality
- Testing
- Continuous Integration
- Technical Debt Management

**Source:** [Code Maintainability](https://dora.dev/capabilities/code-maintainability/)

---

### Continuous Delivery

Continuous delivery (CD) is the practice of keeping software always in a deployable state — every change is automatically built, tested, and packaged for production release at any time. CD does not require deploying every commit automatically (that is continuous deployment), but it requires that deployment always be a business decision, not a technical one.

#### Key Takeaways

- CD is one of the most impactful capabilities in the DORA model: it improves all four key metrics simultaneously.
- The goal is deployability on demand — the system can release at any point, eliminating "release crunch" and the associated rework.
- Documentation quality multiplies CD's effectiveness. DORA research shows teams with quality documentation achieve 656% greater improvement in software delivery performance from CD adoption, versus 63% for teams without it.
- CD requires a supporting foundation: automated testing, trunk-based development, deployment automation, and continuous integration all need to be in place first.
- In AI-accelerated environments, CD becomes even more critical: AI increases the volume of code commits, and CD is the mechanism that ensures quality gates keep pace.
- CD enables fast feedback loops, which are essential for both AI adoption (to see AI's impact on production behavior) and for healthy team learning culture.

#### How to Measure

- % of releases that are one-click (or automated) deployments
- Deployment lead time from code-complete to production-ready
- % of releases that cause an unplanned freeze or manual intervention
- Time spent on release activities per cycle

#### DORA Metrics Impact

CD is the primary driver of **Deployment Frequency** and **Change Lead Time**. By eliminating manual release steps, it compresses the time between development and production. Well-implemented CD also improves **Change Fail Rate** because automated quality gates catch regressions before they reach users.

#### Cost Savings Connection

CD's cost savings span all three value categories in the DORA ROI framework. Rework avoidance: CD eliminates the category of rework caused by large, infrequent releases (integration conflicts, environment drift, regression accumulation). Reinvestment value: teams freed from release coordination can focus on feature delivery. Downtime cost: small, frequent releases are much easier to roll back than large batch releases, dramatically reducing mean time to recovery when failures occur.

#### Related Capabilities

- Continuous Integration
- Trunk-Based Development
- Deployment Automation
- Testing

**Source:** [Continuous Delivery](https://dora.dev/capabilities/continuous-delivery/)

---

### Continuous Integration

Continuous integration (CI) is the practice of merging code changes into a shared branch multiple times per day, with each merge triggering an automated build and test suite. The goal is to surface integration problems quickly rather than allowing them to accumulate into large, expensive release failures.

#### Key Takeaways

- CI is the connective tissue that makes all other delivery capabilities work together: without it, CD, trunk-based development, and testing are disconnected activities.
- Fast feedback is CI's primary value proposition: developers learn within minutes whether their change breaks anything, rather than discovering problems days later.
- DORA research shows that documentation quality dramatically multiplies CI's impact: teams with quality documentation see a 750% greater improvement in software delivery performance from CI, versus 34% for teams without it.
- Security testing should be integrated into CI pipelines (the "shift left" principle), so vulnerabilities are surfaced at the point of introduction rather than post-deployment.
- In AI-accelerated environments, CI is more important than ever: AI increases commit velocity, and CI is the gate that ensures faster commits don't mean more failures.
- A fast CI pipeline (ideally under 10 minutes) is essential for maintaining developer flow state — slow CI negates much of the feedback loop benefit.

#### How to Measure

- % of code changes that trigger an automated build and test run
- CI pipeline execution time (target: under 10 minutes)
- % of CI runs that fail due to test failures (vs. infrastructure issues)
- Time from commit to actionable feedback for the developer

#### DORA Metrics Impact

CI directly improves **Change Lead Time** by eliminating the wait time between code completion and integration feedback. It reduces **Change Fail Rate** by catching regressions early. Teams with fast CI pipelines have significantly higher **Deployment Frequency** because the integration bottleneck is removed.

#### Cost Savings Connection

DORA's rework formula captures the savings from CI most clearly: time spent fixing late-discovered integration problems is a direct component of unnecessary rework cost. High-performing teams with mature CI practices spend far less time on this category of rework. For a 250-person engineering organization, the annual rework cost difference between low and high performers can exceed $800K; CI is one of the primary capabilities that drives that gap.

#### Related Capabilities

- Trunk-Based Development
- Testing
- Continuous Delivery
- Code Maintainability

**Source:** [Continuous Integration](https://dora.dev/capabilities/continuous-integration/)

---

### Customer Feedback

Customer feedback is the systematic practice of gathering, processing, and acting on information about how users experience the software. This includes both formal mechanisms (usage analytics, NPS surveys, support tickets) and informal ones (user interviews, community forums). DORA research shows that teams with strong customer feedback loops have 40% higher organizational performance.

#### Key Takeaways

- User-centric teams outperform teams focused on internal metrics alone by 40% on organizational performance measures — this is one of the strongest findings in recent DORA research.
- The 2025 DORA AI report found that without a user-centric focus, AI adoption has a **negative** impact on team performance. AI amplifies the disconnect when teams build without feedback.
- Only about one-third of features in a mature product deliver top-line value — customer feedback is the primary mechanism for identifying which third that is before building it.
- Feedback loops must be short: the value of feedback degrades with time. Teams should aim for continuous, lightweight feedback rather than periodic large-scale studies.
- Customer feedback is not just a product management discipline — it should inform technical decisions about architecture, reliability, and performance.
- Generative AI can help teams analyze large volumes of customer feedback faster, synthesizing patterns from support tickets and user interactions that would otherwise take weeks to process.

#### How to Measure

- Frequency of customer feedback collection cycles
- Time from feedback receipt to product decision
- Net Promoter Score or customer satisfaction (CSAT) trend
- % of roadmap items with traceable customer feedback origin

#### DORA Metrics Impact

Customer feedback most directly improves the value delivered per deployment — it doesn't show up directly in the four keys but is a leading indicator of whether deployments move the business forward. Teams with strong feedback also tend to have better **Change Fail Rate** because they're less likely to ship features based on incorrect assumptions, which reduces the rework that comes from misaligned product decisions.

#### Cost Savings Connection

DORA's reinvestment value category is where customer feedback's ROI is highest. Time freed from improving delivery can be reinvested in new features — but only if teams are building features users actually want. Given that only about one-third of features deliver top-line value, a team that uses customer feedback to accurately identify that third will generate dramatically more return per engineering dollar than a team building without feedback. The cost of building the wrong features — and then having to rework or discard them — is one of the most significant hidden costs in software organizations.

#### Related Capabilities

- Work Visibility in Value Stream
- User Research and Experimentation
- Learning Culture
- Team Experimentation

**Source:** [Customer Feedback](https://dora.dev/capabilities/customer-feedback/)

---

### Deployment Automation

Deployment automation is the practice of scripting and tooling the full process of releasing software to any environment — development, staging, or production — so that deployments are repeatable, consistent, and require minimal human intervention. It eliminates the class of failures caused by manual deployment steps and enables teams to deploy with confidence and high frequency.

#### Key Takeaways

- Manual deployments are a primary source of both variance (each deployment may be done slightly differently) and rework (errors in manual steps must be diagnosed and corrected).
- Automation is the prerequisite for high deployment frequency — human-dependent processes create a ceiling on how often a team can safely release.
- The automation should include rollback procedures: DORA's 2025 data show that teams with strong rollback capability have significantly lower **Failed Deployment Recovery Time** than those that rely on forward fixes.
- Deployment automation should extend across environments (dev, staging, production), not just production — environment parity is essential for "it works on my machine" problem elimination.
- Progressive delivery patterns (feature flags, canary deployments, blue-green deployments) extend the value of deployment automation by enabling controlled rollouts that reduce blast radius.

#### How to Measure

- % of deployments that are fully automated (no manual steps)
- Deployment success rate (deployments that complete without rollback or intervention)
- Mean deployment duration
- % of environments with automated deployment parity to production

#### DORA Metrics Impact

Deployment automation is the most direct driver of **Deployment Frequency** — without it, teams cannot sustainably deploy multiple times per day. It also compresses **Change Lead Time** by eliminating wait time for deployment slots. When combined with automated rollback, it dramatically reduces **Failed Deployment Recovery Time**.

#### Cost Savings Connection

DORA's downtime cost framework applies most directly here: every minute of production downtime has a quantifiable cost, and deployment automation with rollback capability is the primary mechanism for minimizing that time. Beyond downtime, deployment automation eliminates the rework cost associated with manual deployment errors — a category that compounds significantly at scale. Teams that automate deployment also free senior engineers from release coordination, recovering significant senior engineer time for higher-value work.

#### Related Capabilities

- Continuous Delivery
- Version Control
- Infrastructure as Code
- Continuous Integration

**Source:** [Deployment Automation](https://dora.dev/capabilities/deployment-automation/)

---

### Documentation Quality

Documentation quality is the degree to which internal documentation — architecture diagrams, runbooks, onboarding guides, API references, decision records — is accurate, complete, discoverable, and maintained as a living artifact. DORA research identifies documentation quality as a "force multiplier" capability: it amplifies the impact of nearly every other capability.

#### Key Takeaways

- Documentation quality is one of the most powerful multiplier capabilities in the DORA model. DORA research shows that teams with quality documentation achieve dramatically higher performance improvements from other capabilities:
  - CI: 34% improvement without quality docs → 750% with quality docs
  - Trunk-Based Development: 36% → 1,525%
  - Continuous Delivery: 63% → 656%
- High-quality documentation reduces new developer onboarding time, lowers the expertise barrier for production operations, and enables teams to move faster with less coordination overhead.
- AI amplifies documentation's value: teams with strong internal documentation can use AI tools to synthesize and surface it in context, turning written knowledge into on-demand expertise.
- Documentation must be treated as a first-class engineering artifact — tracked in version control, reviewed alongside code, and updated as part of the definition of done.
- DORA's 2025 research confirmed that teams prioritizing documentation quality have higher individual well-being and job satisfaction, likely because they spend less time on frustrating knowledge-search activities.

#### How to Measure

- Developer experience survey: "I can find the documentation I need to do my work" (1–7 scale)
- Time to locate architectural context for an unfamiliar service
- % of runbooks tested in incident simulations
- Onboarding time to first production contribution

#### DORA Metrics Impact

Documentation quality has a compounding effect on all four metrics. It reduces **Change Lead Time** by lowering cognitive friction. It reduces **Change Fail Rate** by ensuring developers understand the systems they're modifying. It reduces **Failed Deployment Recovery Time** by making runbooks and recovery procedures findable in a crisis. Teams with strong documentation also have higher **Deployment Frequency** because the knowledge required to deploy safely is democratized rather than locked in individual experts.

#### Cost Savings Connection

Documentation quality generates ROI across all three DORA value categories. Rework avoidance: well-documented systems reduce the category of mistakes caused by misunderstanding architecture or existing behavior. Reinvestment value: teams that don't spend time searching for context can spend that time shipping features. Downtime cost: accurate, tested runbooks compress the Mean Time to Resolution for every incident. The multiplication effect documented by DORA research means that investments in documentation quality have an outsized return when other capabilities are also in place.

#### Related Capabilities

- Code Maintainability
- Continuous Integration
- Onboarding
- Knowledge Sharing

**Source:** [Documentation Quality](https://dora.dev/capabilities/documentation-quality/)

---

### Flexible Infrastructure

Flexible infrastructure is the ability to provision, scale, and reconfigure compute, storage, and networking resources on demand — typically via cloud platforms or infrastructure-as-code tooling. It enables teams to match capacity to demand dynamically rather than over-provisioning for peak load or under-provisioning and accepting degraded performance.

#### Key Takeaways

- DORA research consistently shows that teams with on-demand, self-service infrastructure have significantly better software delivery performance than teams dependent on slow provisioning processes.
- The key attributes of flexible infrastructure, according to DORA research: on-demand self-service, broad network access, resource pooling, rapid elasticity, and measured service.
- Infrastructure as code (IaC) is the mechanism that makes flexibility and repeatability compatible — it ensures infrastructure is reproducible, version-controlled, and auditable.
- Flexible infrastructure enables experimentation at scale: teams can spin up test environments for each pull request and tear them down automatically, eliminating environment-related bottlenecks.
- Cloud adoption alone is not sufficient — many organizations run inflexible workflows on flexible infrastructure. The capability is in the workflow, not just the platform.

#### How to Measure

- Time to provision a new development or test environment
- % of infrastructure changes managed via IaC (not manual console operations)
- Environment parity score between development, staging, and production
- Cost efficiency metrics (resource utilization rates)

#### DORA Metrics Impact

Flexible infrastructure primarily improves **Deployment Frequency** and **Change Lead Time** by removing environment bottlenecks. Teams that can provision environments on-demand have no infrastructure-caused wait time in their deployment pipeline. It also reduces **Change Fail Rate** by enabling production-parity testing environments.

#### Cost Savings Connection

Flexible infrastructure generates savings through two mechanisms in the DORA ROI framework: rework avoidance (environment inconsistency is eliminated as a failure category) and downtime reduction (auto-scaling prevents capacity-related incidents). On-demand provisioning also eliminates the coordination overhead of environment scheduling, recovering significant time across engineering teams. Infrastructure efficiency gains (pay-per-use vs. over-provisioned on-premise) are an additional, often substantial, cost reduction.

#### Related Capabilities

- Deployment Automation
- Infrastructure as Code
- Continuous Integration
- Monitoring and Observability

**Source:** [Flexible Infrastructure](https://dora.dev/capabilities/flexible-infrastructure/)

---

### Generative Organizational Culture

Generative organizational culture, based on the Westrum organizational typology, is characterized by high levels of cooperation, information flow, shared risk, bridging between teams, and learning from failures. Westrum identified three culture types — pathological (power-oriented), bureaucratic (rule-oriented), and generative (performance-oriented) — and DORA research consistently finds generative culture as a strong predictor of software delivery performance and employee well-being.

#### Key Takeaways

- Culture is not "soft" — it is a measurable predictor of delivery performance. DORA research shows that Westrum cultural typology is one of the strongest leading indicators of both DORA metric performance and organizational outcomes.
- Psychological safety is the enabling condition for everything else: teams that fear blame will hide failures, avoid experimentation, and under-report incidents — all of which lead to systemic performance decay.
- The 2025 DORA report found that AI adoption has significantly better outcomes in generative cultures: teams with psychological safety treat AI as a tool to learn with, not a threat to hide from.
- Conway's Law states that system architecture mirrors communication structures — organizations with siloed cultures build siloed systems that are hard to change. The Inverse Conway Maneuver deliberately restructures teams to produce better architectures.
- High performers are 2.2 times more likely to recommend their organization as a great place to work, and replacing a departed team member costs approximately 21% of that employee's annual salary. Culture is a direct driver of retention economics.

#### How to Measure

- Westrum cultural survey (validated 7-item scale measuring information sharing, cooperation, and learning from failure)
- eNPS (Employee Net Promoter Score) as a retention proxy
- Incident report frequency and blameless postmortem adoption rate
- % of retrospective action items that result in measurable change

#### DORA Metrics Impact

Generative culture improves all four DORA metrics by enabling the behaviors that make other capabilities work. Teams with high psychological safety communicate failures faster (improving **Failed Deployment Recovery Time**), take more improvement actions (improving all metrics over time), and adopt new practices more quickly. Cultural health is also the substrate on which AI capabilities must be built.

#### Cost Savings Connection

Culture's ROI is most visible in retention and rework. High-performing, satisfied teams have lower turnover: given a replacement cost of ~21% of annual salary, retaining just two senior engineers annually pays for significant culture improvement investment. Generative cultures also have lower rework rates because information flows freely — problems are surfaced and addressed early rather than discovered late at high cost. DORA research shows that high performers significantly outperform low performers on the organizational goal attainment measures that drive revenue and mission.

#### Related Capabilities

- Transformational Leadership
- Learning Culture
- Psychological Safety
- Work Visibility in Value Stream

**Source:** [Generative Organizational Culture](https://dora.dev/capabilities/generative-organizational-culture/)

---

### Job Satisfaction

Job satisfaction in the DORA model is a composite organizational outcome — reflecting burnout levels, individual productivity, and how well employees feel their skills are matched to their work. DORA research treats job satisfaction not just as an employee wellness metric but as a leading indicator of team performance, retention, and organizational health.

#### Key Takeaways

- DORA research identifies job satisfaction as both a driver and an outcome of high performance: satisfied developers are more productive, and high-performing teams have more satisfied members.
- The 2025 DORA report found that AI adoption is associated with reduced burnout and higher job satisfaction when implemented well — but that this improvement is contingent on strong foundational capabilities (culture, documentation, platform quality).
- Teams with high job satisfaction have significantly lower attrition, which has direct cost implications given the ~21% of annual salary cost to replace a technical employee.
- Burnout is a specific and serious risk in software organizations: DORA research distinguishes burnout from general dissatisfaction and shows that it is predictive of both performance decline and departure.
- Empowering teams to choose their own tools (including AI tools) is positively correlated with job satisfaction — autonomy over tooling is not a luxury but a performance driver.

#### How to Measure

- DORA's validated job satisfaction survey scale
- Burnout indicators: emotional exhaustion, depersonalization, sense of ineffectiveness
- Voluntary attrition rate and exit interview themes
- Developer experience pulse surveys (quarterly or more frequent)

#### DORA Metrics Impact

Job satisfaction does not directly map to a single DORA metric but influences all four through its effect on team engagement, knowledge retention, and willingness to invest in improvement work. Teams with high job satisfaction are more likely to invest discretionary effort in the capability improvements that drive DORA metric performance.

#### Cost Savings Connection

The most direct cost savings from job satisfaction are in retention. Replacing a departing technical employee costs approximately 21% of their annual salary — factoring in recruiting, onboarding, and the productivity ramp for their replacement. For an organization with 100 technical employees and an average salary of $143K, reducing voluntary attrition by just 2 percentage points saves approximately $600K annually. DORA research also links job satisfaction to higher individual productivity, which compounds across the team's capacity for feature delivery.

#### Related Capabilities

- Generative Organizational Culture
- Transformational Leadership
- Psychological Safety
- Well-Being

**Source:** [Job Satisfaction](https://dora.dev/capabilities/job-satisfaction/)

---

### Loosely Coupled Teams

Loosely coupled teams are organized so that individual teams can design, build, test, and deploy their service independently — without requiring coordination with or approval from other teams. This architectural and organizational pattern, consistent with microservices and domain-driven design principles, is the organizational expression of Conway's Law.

#### Key Takeaways

- DORA research consistently identifies team coupling as one of the most powerful architectural and organizational variables for delivery performance. Tightly coupled teams face coordination bottlenecks that no tooling can fully overcome.
- The 2025 DORA data include evidence from Adidas: loosely coupled teams using AI saw 20–30% productivity gains; tightly coupled teams saw no significant benefit. Coupling absorbs AI productivity gains.
- The Inverse Conway Maneuver — restructuring teams to produce the desired architecture — is the recommended path to decoupling. Architecture change without team structure change is fragile.
- Decoupling enables parallel delivery: multiple teams can ship independently without release coordination, dramatically increasing overall organizational throughput.
- Loose coupling is not just technical — it requires team charters with clear ownership boundaries, APIs as contracts, and tolerant reader patterns for cross-team data exchange.

#### How to Measure

- % of team deployments that require coordination with another team
- Team autonomy index (survey: "My team can deploy without waiting for other teams")
- Number of cross-team approval dependencies per deployment
- Lead time variance (high variance often indicates hidden coupling)

#### DORA Metrics Impact

Loosely coupled teams have dramatically higher **Deployment Frequency** because there are no coordination bottlenecks. They have lower **Change Lead Time** because review and approval chains are shorter. They also tend to have lower **Change Fail Rate** because changes are smaller and more contained — blast radius is limited by design.

#### Cost Savings Connection

Coupling creates coordination overhead that shows up as rework cost — time spent negotiating releases, waiting for approvals, and debugging cross-team integration failures. DORA's rework formula captures this: every hour a developer waits for another team is an hour of unnecessary overhead. For AI adoption specifically, coupling is the single biggest reason AI fails to deliver organizational value. The Adidas data point illustrates that loosely coupled teams can convert AI investment into measurable productivity gains while tightly coupled teams cannot — making decoupling a prerequisite for AI ROI.

#### Related Capabilities

- Generative Organizational Culture
- Deployment Automation
- Service Reliability
- Work Visibility in Value Stream

**Source:** [Loosely Coupled Teams](https://dora.dev/capabilities/loosely-coupled-teams/)

---

### Monitoring and Observability

Monitoring and observability (M&O) encompasses the instrumentation, tooling, and practices that allow teams to understand what their systems are doing in production. Monitoring tracks known failure modes with predefined alerts; observability enables exploration of unknown failure modes by providing structured access to telemetry data (logs, metrics, traces).

#### Key Takeaways

- DORA research places M&O among the top technical capabilities for predicting software delivery performance. Teams that can observe their systems make better decisions faster.
- The distinction between monitoring and observability matters operationally: monitoring tells you something is wrong; observability tells you why.
- In AI-accelerated environments, observability becomes critical for a new reason: AI can introduce subtle regressions that look correct in tests but produce unexpected production behavior — only production observability can catch these.
- Effective M&O enables proactive failure detection (catching issues before users do) and reduces **Failed Deployment Recovery Time** by providing actionable incident context immediately.
- Distributed tracing is increasingly essential as microservices architectures create complex, distributed failure modes that traditional log-based monitoring cannot efficiently diagnose.

#### How to Measure

- Mean Time to Detection (MTTD) for production incidents
- Mean Time to Resolution (MTTR) for production incidents
- % of incidents detected by internal monitoring (vs. reported by users)
- Developer experience survey: "I have the observability tools I need to understand production behavior" (1–7 scale)

#### DORA Metrics Impact

M&O most directly improves **Failed Deployment Recovery Time** — teams with rich observability data resolve incidents faster. It also reduces **Change Fail Rate** by enabling faster detection of regressions introduced by new deployments, shortening the window between deployment and rollback decision. Over time, observability data informs architecture decisions that reduce future failures.

#### Cost Savings Connection

The DORA ROI framework's downtime cost category is where M&O's impact is most direct. Every minute of reduced MTTR directly reduces downtime cost — and for high-traffic systems, downtime cost can be thousands of dollars per minute. Proactive detection (catching issues before users do) avoids the reputation cost of user-visible failures, which DORA research shows affects both customer retention and developer morale. Teams with strong observability also have lower rework costs because they spend less time on exploratory debugging and more time on targeted fixes.

#### Related Capabilities

- Service Reliability
- Deployment Automation
- Flexible Infrastructure
- Continuous Integration

**Source:** [Monitoring and Observability](https://dora.dev/capabilities/monitoring-and-observability/)

---

### Pervasive Security

Pervasive security is the integration of security practices — threat modeling, automated security testing, dependency scanning, access control review — throughout the software delivery lifecycle rather than as a final gate before production. This "shift left" approach means security is everyone's responsibility, not the security team's bottleneck.

#### Key Takeaways

- DORA research shows that teams with pervasive security practices have better delivery performance than teams that treat security as a separate, late-stage process. Security and speed are not trade-offs.
- "Shift left" is the operational principle: catching security vulnerabilities at the point of code introduction is dramatically cheaper than catching them in production.
- AI dramatically increases the volume of code being written and merged — making automated security scanning in CI pipelines even more critical. AI-generated code must be subject to the same security gates as human-written code.
- Supply chain security (software composition analysis, dependency auditing) is an increasingly critical component of pervasive security as the proportion of third-party and AI-generated code grows.
- Security teams should function as enablers (providing tooling, training, and standards) rather than gatekeepers (reviewing every change).

#### How to Measure

- % of services with automated security scanning in CI pipelines
- Mean time from vulnerability discovery to remediation
- % of developers who have completed security training
- SAST/DAST coverage across production services

#### DORA Metrics Impact

Pervasive security reduces **Change Fail Rate** by catching vulnerabilities before they reach production — security incidents are a major category of change failures. It also supports **Deployment Frequency** by eliminating the late-stage security review bottleneck. When security is automated in CI, each pipeline run is also a security check, compressing **Change Lead Time**.

#### Cost Savings Connection

Security incident costs are often the largest single-event cost a software organization faces. DORA's downtime cost framework applies directly: security incidents cause downtime, customer data exposure, and regulatory fines. Catching a vulnerability in CI costs developer time measured in minutes; catching it in production costs organizational time measured in days to weeks, plus incident response, legal, and reputational costs. Pervasive security practices move the detection and remediation cost from the most expensive point (production) to the least expensive point (development).

#### Related Capabilities

- Continuous Integration
- Deployment Automation
- Supply Chain Security
- Code Maintainability

**Source:** [Pervasive Security](https://dora.dev/capabilities/pervasive-security/)

---

### Teams Empowered to Choose Tools

This capability describes the degree to which development teams have autonomy to select the tools, frameworks, and technologies that best fit their work — rather than having them mandated top-down by IT governance or architecture councils. DORA research shows tool autonomy is positively correlated with both performance and job satisfaction.

#### Key Takeaways

- Autonomy over tooling is not just a morale issue — it is a performance driver. Teams that choose their own tools are more invested in using them well and more likely to adopt them fully.
- The 2025 DORA data show that empowering teams to choose AI tools specifically is associated with higher job satisfaction and better AI adoption outcomes.
- Tool autonomy must be bounded: freedom to choose tools must be balanced by organization-wide constraints on cost, compliance, security, and interoperability. The "clear AI stance" capability is the mechanism for setting those constraints.
- Governance that mandates a single tool for all teams often produces compliance without adoption — teams use the approved tool minimally while working around it with unofficial alternatives.
- Federated governance models (org-wide standards for interfaces and security, team autonomy for implementation choices) are the pattern that balances standardization with autonomy.

#### How to Measure

- Developer experience survey: "My team has the authority to choose the tools and technologies we need to do our work" (1–7 scale)
- % of teams using a tool because it was the best fit vs. because it was mandated
- Time to adopt a new tool or technology (approval process duration)

#### DORA Metrics Impact

Tool autonomy improves **Change Lead Time** and **Deployment Frequency** by enabling teams to eliminate friction in their specific workflow rather than adapting to a generic toolset. Teams empowered to choose their tools also tend to invest more in CI and automation, which compounds across all four metrics.

#### Cost Savings Connection

Tool autonomy's cost savings come primarily from reinvestment value: teams using well-fitted tools are more productive, with higher engagement, and lower attrition. Given the ~21% of salary replacement cost for departed technical employees, retaining engaged, autonomous developers is a direct financial benefit. Tool mandates that produce disengagement are a hidden attrition risk with calculable financial consequences.

#### Related Capabilities

- Generative Organizational Culture
- Clear AI Stance
- Job Satisfaction
- Learning Culture

**Source:** [Teams Empowered to Choose Tools](https://dora.dev/capabilities/teams-empowered-to-choose-tools/)

---

### Testing

Testing in the DORA model encompasses the full range of automated testing practices — unit tests, integration tests, end-to-end tests, contract tests, and performance tests — that provide developers with confidence that their changes work as intended. It is the safety net that enables high deployment frequency without proportional increases in failure rate.

#### Key Takeaways

- Testing is one of the earliest and most robustly replicated findings in DORA research: teams with strong test coverage deploy more frequently and have lower failure rates.
- Reliable tests are more valuable than comprehensive tests: a flaky test suite that produces false positives trains developers to ignore test failures, which eliminates the feedback loop benefit.
- Test-driven development (TDD) combines testing with code design, producing more maintainable code and higher test quality simultaneously.
- AI can accelerate test creation (generating test scaffolding, suggesting edge cases) — but AI-generated tests require the same review as AI-generated production code. Tests that pass but don't actually verify behavior are worse than no tests.
- Trunk-based development requires comprehensive automated testing: with everyone committing to the main branch frequently, automated tests are the primary mechanism for detecting regressions before they affect other developers.
- Contract testing between services is essential for loosely coupled architectures: it enables teams to deploy independently while still catching cross-service compatibility issues.

#### How to Measure

- Code coverage (line, branch, and statement) as a baseline measure
- Test reliability: flakiness rate (% of test runs with intermittent failures)
- Time from code change to test feedback (should be minutes, not hours)
- % of production incidents that had a corresponding missed test

#### DORA Metrics Impact

Testing is the primary mechanism that prevents **Change Fail Rate** from rising as **Deployment Frequency** increases. Without it, faster deployments mean faster failures. Testing also directly improves **Change Lead Time** by providing automated feedback that eliminates manual verification steps.

#### Cost Savings Connection

Testing's cost savings are clearest in rework avoidance. Defects caught in testing cost a fraction of defects caught in production — the ratio depends on the complexity of the system but typically ranges from 5:1 to 100:1. DORA's rework formula directly captures this: the % of time on unnecessary rework is substantially driven by the rate of defects reaching production. Teams with strong test coverage spend significantly less time on unplanned recovery work, which is the single largest component of the rework cost formula.

#### Related Capabilities

- Continuous Integration
- Code Maintainability
- Trunk-Based Development
- Deployment Automation

**Source:** [Testing](https://dora.dev/capabilities/test-automation/)

---

### Trunk-Based Development

Trunk-based development (TBD) is the practice of having all developers integrate their changes into a single shared branch (trunk/main) at least once per day, using short-lived feature branches that last no more than a few days. It is the branching strategy that makes continuous integration possible at scale.

#### Key Takeaways

- DORA research identifies TBD as one of the most impactful technical practices for delivery performance. Long-lived feature branches are one of the most common sources of integration complexity and delay.
- Documentation quality multiplies TBD's impact: teams with quality documentation see a 1,525% greater improvement in software delivery performance from TBD adoption, versus 36% for teams without it — the largest documented multiplier effect in DORA research.
- TBD requires feature flags as a complementary practice: to commit unfinished features to trunk without shipping them to users, teams need flags that decouple deployment from release.
- Teams moving from long-lived feature branches to TBD often experience a short-term disruption (the "J-curve") before seeing performance improvements. Leadership support during this transition is critical.
- Code review must be fast to support TBD: DORA research shows that teams with fast code reviews (under 24 hours) have 50% better software delivery performance than teams with slow reviews.

#### How to Measure

- % of developers committing to trunk at least once per day
- Average feature branch lifetime (target: under 2 days)
- % of merges that trigger a CI failure (higher early in TBD adoption, should decrease over time)
- Code review turnaround time

#### DORA Metrics Impact

TBD directly improves **Deployment Frequency** by eliminating the integration overhead of long-lived branches. It improves **Change Lead Time** by keeping changes small and reviewable. When combined with feature flags, it also reduces **Change Fail Rate** because releases can be decoupled from deployments, enabling safer progressive rollouts.

#### Cost Savings Connection

TBD's primary cost savings come from eliminating merge conflicts and integration rework. DORA research shows that long-lived feature branches are one of the most significant sources of integration-related rework — the cost of resolving conflicts between branches that have diverged for weeks or months. This rework appears directly in DORA's rework formula as unnecessary time. For organizations with many developers working in parallel, the cumulative merge conflict resolution cost can represent a substantial fraction of total engineering time.

#### Related Capabilities

- Continuous Integration
- Testing
- Feature Flags
- Documentation Quality

**Source:** [Trunk-Based Development](https://dora.dev/capabilities/trunk-based-development/)

---

### Well-Being

Well-being in DORA's model is a composite capability reflecting the degree to which software delivery work supports the mental and physical health of team members. It encompasses burnout prevention, workload sustainability, psychological safety, and conditions for finding meaning in work. DORA research treats well-being both as an outcome worth pursuing and as a predictor of team and organizational performance.

#### Key Takeaways

- DORA research shows that software delivery performance and well-being are mutually reinforcing: high-performing teams have better well-being, and teams with better well-being perform better.
- The 2025 DORA report found that AI adoption is associated with reduced burnout and increased productivity — but this improvement is conditional on strong foundational capabilities. Without them, AI creates pressure ("work intensification") without delivering relief.
- Work intensification is a documented phenomenon: AI increases individual output, which often leads to increased expectations of output, leaving burnout levels unchanged. Leaders must manage for sustainability, not just throughput.
- Change failure and incident response are among the most significant burnout drivers: teams that are constantly fighting production fires have neither the time nor the psychological energy to improve.
- Sustainable pace is a precondition for continuous improvement: teams that are chronically overworked skip improvement work, which creates a negative cycle of degrading performance and increasing load.

#### How to Measure

- DORA's validated well-being scale (burnout, productivity, job satisfaction composite)
- Unplanned work ratio (% of work that is reactive vs. planned)
- After-hours incident response frequency
- Voluntary attrition rate

#### DORA Metrics Impact

Well-being influences all four metrics through its effect on engagement, knowledge sharing, and willingness to invest in improvement. Teams with poor well-being have higher **Change Fail Rate** (due to shortcuts under pressure) and longer **Failed Deployment Recovery Time** (due to alert fatigue and under-staffed on-call rotations).

#### Cost Savings Connection

Well-being's financial case runs through retention and productivity. Attrition costs ~21% of annual salary per departing employee. Burnout-related productivity loss and absenteeism are additional costs that DORA research links to deployment performance. Teams with poor well-being also have higher incident rates, which multiplies downtime costs. The ROI of investing in well-being — through realistic workloads, blameless postmortems, and sustainable on-call practices — is measurable through the combination of attrition reduction and incident cost reduction.

#### Related Capabilities

- Generative Organizational Culture
- Job Satisfaction
- Transformational Leadership
- Monitoring and Observability

**Source:** [Well-Being](https://dora.dev/capabilities/well-being/)

---

## Secondary Capabilities

Secondary capabilities are practices with strong empirical support in DORA research that amplify the impact of core capabilities or address specific organizational contexts. They are not "optional" — for many teams, one or more of these will be the highest-leverage improvement opportunity.

---

### Infrastructure as Code

Infrastructure as code (IaC) is the practice of managing and provisioning infrastructure (servers, networks, databases, configuration) through machine-readable definition files rather than manual processes or interactive configuration tools. It applies software engineering discipline to infrastructure management.

#### Key Takeaways

- IaC is the mechanism that makes flexible infrastructure repeatable and auditable: without it, on-demand provisioning creates consistency risks over time.
- Version-controlled infrastructure definitions make infrastructure changes subject to the same review, testing, and rollback mechanisms as application code.
- IaC is a prerequisite for production-parity test environments at scale: manually configured environments inevitably drift from production.
- Drift detection — automatically identifying when real infrastructure state diverges from defined state — is a critical complementary practice that prevents IaC from becoming a false sense of control.

#### How to Measure

- % of infrastructure changes made via IaC (vs. manual console operations)
- Infrastructure drift detection coverage
- Mean time to provision a new environment via IaC
- % of infrastructure configurations tracked in version control

#### DORA Metrics Impact

IaC improves **Deployment Frequency** by enabling on-demand environment creation. It reduces **Change Fail Rate** caused by environment inconsistency. Automated rollback of infrastructure changes also improves **Failed Deployment Recovery Time**.

#### Cost Savings Connection

IaC eliminates a category of rework caused by environment drift and manual configuration errors — both of which appear in DORA's rework formula. It also reduces the time required to provision new environments for experiments, accelerating the reinvestment value that comes from freed-up developer time.

#### Related Capabilities

- Flexible Infrastructure
- Deployment Automation
- Version Control
- Continuous Integration

**Source:** [Infrastructure as Code](https://dora.dev/capabilities/infrastructure-as-code/)

---

### Learning Culture

A learning culture is an organizational environment in which seeking knowledge, experimenting with new approaches, sharing findings openly, and learning from both successes and failures are actively encouraged and structurally supported. DORA research identifies learning culture as a predictor of software delivery performance.

#### Key Takeaways

- DORA research shows that a learning culture is predictive of software delivery performance — not just a "nice to have" environment attribute.
- High-performing teams favor communities of practice and grassroots strategies for spreading knowledge; low performers rely on centers of excellence (CoE). CoEs create bottlenecks and exclusive expert groups that can't scale, whereas communities of practice build distributed, sustainable capability.
- The 2025 DORA AI guide found that generative AI can support learning culture by acting as a "virtual peer programming" experience — providing code explanations, suggesting edge cases, and helping developers understand unfamiliar systems. But this requires AI to be seen as a learning tool, not just a productivity tool.
- AI dependency is a real concern: DORA's research with student developers found active self-regulation strategies emerging — deliberately attempting problems before using AI, line-by-line verification of AI output, alternating between assisted and unassisted work. These strategies reflect a healthy learning culture.
- Blameless postmortems are the archetypal learning culture practice for production failures: they reframe incidents as learning opportunities rather than occasions for punishment.

#### How to Measure

- % of incidents with completed blameless postmortems
- Number of communities of practice active in the organization
- Developer experience survey: "My organization supports learning and experimentation" (1–7 scale)
- % of improvement ideas from retrospectives that are implemented

#### DORA Metrics Impact

Learning culture drives improvement across all four metrics over time by enabling teams to identify and act on root causes of performance gaps. It also moderates the **Change Fail Rate** reduction from other capabilities by ensuring teams adapt practices to their specific context rather than applying them dogmatically.

#### Cost Savings Connection

Learning culture's ROI is most visible in the long run through capability accumulation. Organizations that invest in learning build durable advantages: improvements compound rather than being one-time gains. Communities of practice, in particular, are more cost-effective than training centers for spreading knowledge: they leverage internal expertise, operate continuously rather than episodically, and build organizational resilience to re-organizations and product changes.

#### Related Capabilities

- Generative Organizational Culture
- Transformational Leadership
- Team Experimentation
- Documentation Quality

**Source:** [Learning Culture](https://dora.dev/capabilities/learning-culture/)

---

### Service Reliability

Service reliability is the disciplined practice of defining, measuring, and managing the availability, latency, and correctness of production services. It encompasses SLOs (service level objectives), SLIs (service level indicators), error budgets, and the operational practices that keep services within their reliability targets.

#### Key Takeaways

- DORA research frames reliability as an engineering discipline, not a heroics discipline: reliable services are built through systematic practice, not through on-call engineers firefighting around the clock.
- SLOs convert reliability from a vague goal into a measurable target: they define exactly what "reliable enough" means for a given service, enabling data-driven trade-off decisions between feature velocity and stability.
- Error budgets — the permissible amount of unreliability remaining within the SLO — create a shared language for the velocity-vs.-stability trade-off. When the budget is healthy, teams can take more deployment risk; when it's depleted, stability becomes the priority.
- Reliability work directly reduces the on-call burden that is one of the most significant burnout drivers for software teams.
- AI can assist with reliability analysis (anomaly detection in metrics, predicting failure patterns), but requires healthy data ecosystems to be effective.

#### How to Measure

- SLO attainment rate across production services
- Error budget consumption rate
- Mean Time Between Failures (MTBF)
- On-call incident burden (alerts per engineer per week)

#### DORA Metrics Impact

Service reliability most directly improves **Failed Deployment Recovery Time** by making recovery procedures systematic and rehearsed. Well-designed SLOs also reduce **Change Fail Rate** by providing clear signals for when deployments have degraded service behavior. Reliability engineering practices (chaos engineering, game days) build organizational resilience that appears across all four metrics.

#### Cost Savings Connection

Reliability directly addresses the downtime cost component of DORA's ROI framework. Each percentage point of uptime improvement translates to quantifiable avoided downtime cost — for high-traffic services, this can be thousands of dollars per minute. Reliability practices also reduce the hidden cost of on-call burden: engineer time spent on-call managing incidents is one of the largest components of maintenance overhead, and reducing incident frequency and duration recovers that time for value-creating work.

#### Related Capabilities

- Monitoring and Observability
- Deployment Automation
- Well-Being
- Testing

**Source:** [Service Reliability](https://dora.dev/capabilities/service-reliability/)

---

### Team Experimentation

Team experimentation is the practice of teams independently designing and running experiments to test hypotheses about their software, processes, or practices — and using the results to inform decisions. It is the operational expression of a scientific mindset applied to software delivery improvement.

#### Key Takeaways

- DORA research shows that teams with autonomy to experiment outperform teams that rely on top-down process prescription.
- The PDCA (Plan-Do-Check-Act) cycle, also known as the Deming cycle, is the recommended framework for structured experimentation: plan the expected outcome, run the experiment, study the results, and decide what to do next.
- Teams should set their own OKRs (objectives and key results) rather than having goals imposed top-down — teams without ownership of their goals will optimize metrics artificially rather than improving genuinely.
- Stretch goals are expected to be partially missed: DORA's transformation research recommends aiming to achieve about 80% of goals, and notes that teams starting cultural transformation often don't achieve any of their first iteration's goals — the learning itself is the value.
- Capacity for experimentation must be protected: improvement work competes with delivery work, and teams that don't protect time for experiments will always choose delivery, gradually degrading performance.
- The J-curve is the expected pattern for new practice adoption: performance often dips before improving. Leaders must understand and accept this pattern to avoid killing experiments prematurely.

#### How to Measure

- Number of improvement experiments run per quarter
- % of retrospective action items implemented and measured
- Team autonomy index (survey: "My team has the authority to make decisions about our processes")
- Lead time to implement a process improvement idea

#### DORA Metrics Impact

Team experimentation drives improvement across all four metrics over time by creating a learning system that continuously finds and tests better approaches. It is the primary mechanism for moving from one performance tier to the next. Without it, teams plateau even when they have good foundational practices.

#### Cost Savings Connection

Team experimentation's ROI comes from the accumulated value of improvements compounded over time. Each experiment that finds a more effective approach generates savings that persist indefinitely. The alternative — relying on top-down transformation programs — is documented in DORA research as frequently failing, consuming significant resources without generating lasting improvement. DORA's transformation research shows that top-down transformation programs often follow a pattern of temporary improvement followed by regression to baseline, consuming investment without generating durable returns.

#### Related Capabilities

- Learning Culture
- Transformational Leadership
- Generative Organizational Culture
- Working in Small Batches

**Source:** [Team Experimentation](https://dora.dev/capabilities/team-experimentation/)

---

### Transformational Leadership

Transformational leadership in DORA's model describes leaders who inspire vision, foster an environment of psychological safety and learning, support their teams' autonomy, and remove organizational impediments. DORA research consistently identifies leadership quality as a strong predictor of both team capability development and organizational outcomes.

#### Key Takeaways

- Transformational leaders enable capabilities; transactional leaders monitor compliance. DORA research shows that the transformational style produces dramatically better performance outcomes.
- Leaders are responsible for setting direction (the "true north") and then empowering teams to determine how to get there — not prescribing the how. When leaders mandate both what and how, teams lose the autonomy and ingenuity that produces high performance.
- The DORA transformation guide recommends communities of practice and grassroots approaches over Centers of Excellence for spreading DevOps and agile methods. CoEs create bottlenecks and isolated expertise; communities of practice build distributed, sustainable capability.
- Treating transformation as a one-time project or as a purely top-down effort are the two most commonly cited failure modes in DORA's organizational change research.
- Leaders must protect improvement capacity: teams that are constantly fully allocated to delivery work have no capacity to improve, creating a trap that only leadership can break by explicitly allocating time for improvement.
- Measurement brings risk: the same metrics that drive high performance can damage cultural conditions when used punitively. Leaders must use metrics to learn, not to punish.

#### How to Measure

- Transformational leadership survey (validated DORA scale measuring vision, inspiration, intellectual stimulation, and supportive environment)
- % of teams with protected improvement time
- Frequency of leadership engagement with team-level improvement work
- Organizational cultural score (Westrum typology)

#### DORA Metrics Impact

Transformational leadership is a leading indicator for all four DORA metrics because it creates the conditions — safety, autonomy, capacity — in which all other capability improvements are possible. Organizations with weak transformational leadership consistently plateau even when individual practices are technically sound.

#### Cost Savings Connection

Leadership quality's ROI is most clearly seen in transformation outcomes. DORA's research shows that top-down transformation programs frequently fail, consuming resources and organizational capacity without generating lasting improvement — and creating cynicism and disengagement that persists long after the program ends. Leaders who invest in creating the conditions for grassroots improvement generate compound returns: each capability improvement built organically becomes durable rather than dependent on top-down enforcement. High-performing organizations with strong leadership also have lower attrition — the 21% of salary replacement cost applies here — and better goal attainment across commercial and non-commercial measures.

#### Related Capabilities

- Generative Organizational Culture
- Learning Culture
- Team Experimentation
- Job Satisfaction

**Source:** [Transformational Leadership](https://dora.dev/capabilities/transformational-leadership/)

---

### User-Centric Focus

User-centric focus is the organizational practice of continuously orienting software design and delivery decisions around the needs, behaviors, and feedback of the people who actually use the software. DORA research shows this is one of the strongest predictors of organizational performance.

#### Key Takeaways

- DORA research found that user-centric teams have **40% higher organizational performance** than teams focused primarily on internal metrics. This is one of the largest effect sizes in recent DORA findings.
- The 2025 DORA data show that without a user-centric focus, AI adoption has a **negative** impact on team performance. AI amplifies existing disconnects from user needs.
- Only about one-third of features in a mature product deliver top-line value — user centrism is the primary mechanism for identifying which features those are before building them.
- User-centric focus requires feedback infrastructure: without mechanisms to collect, analyze, and act on user feedback, teams operate on assumptions that compound into wasted investment.
- The most effective user-centric practices involve continuously building, measuring, and learning from real user behavior in production — not just conducting upfront user research.

#### How to Measure

- % of roadmap items with traceable user research or feedback
- Feature adoption and engagement rate post-launch
- Customer satisfaction and NPS trends
- Time from user feedback identification to product response

#### DORA Metrics Impact

User-centric focus does not directly map to a specific DORA metric but is a leading indicator of whether high delivery performance translates into organizational value. Teams that deploy frequently but build features users don't want are not generating organizational performance improvement. User centrism ensures that deployment velocity is converted into value.

#### Cost Savings Connection

The ROI of user-centric focus runs through reinvestment value: the savings from deploying frequently only generate returns if the features being deployed are the ones users need. Given that only about one-third of features deliver top-line value, teams that accurately identify that third generate dramatically more return per engineering dollar. The cost of building and maintaining features that users don't use is a significant, often unmeasured waste in most software organizations.

#### Related Capabilities

- Customer Feedback
- Team Experimentation
- Work Visibility in Value Stream
- Generative Organizational Culture

**Source:** [User-Centric Focus](https://dora.dev/capabilities/user-centric-focus/)

---

### Work Visibility in Value Stream

Work visibility in value stream is the practice of making the entire flow of work — from idea to production — transparent and accessible to all stakeholders. It encompasses value stream mapping (VSM), Kanban boards, metrics dashboards, and any practice that helps teams understand where work is, where it's stuck, and what the systemic constraints on flow are.

#### Key Takeaways

- Value Stream Mapping (VSM) is the recommended technique for establishing work visibility at the systems level. VSM maps the full end-to-end flow from ideation to delivery, making bottlenecks and wait times visible to the entire team.
- DORA recommends outcome mapping before VSM: before mapping the value stream, teams should agree on the specific improvement outcome they're pursuing. Countless improvements can be identified; only those that affect the target outcome matter.
- There are two critical value streams in software delivery: the **happy path** (normal feature delivery, measured by lead time and deployment frequency) and the **recovery value stream** (incident response, measured by change fail rate and failed deployment recovery time). Both must be mapped and optimized.
- VSM data precision should be low: most teams don't have precise metrics for each step, and that's acceptable. Steps that take minutes vs. days are easy to distinguish without instrumentation; improvements measured in minutes won't matter in a process that takes weeks.
- VSM is a force multiplier for AI: it identifies the actual system-level constraint, ensuring AI is applied to clearing real bottlenecks rather than generating more throughput that the downstream system can't absorb.
- DORA recommends an impartial external facilitator for VSM exercises to avoid internal politics distorting the honest assessment of where constraints exist.

#### How to Measure

- Lead time visibility: can teams report where each in-flight work item is in the delivery process in real time?
- % of delivery steps with quantified wait times
- Team agreement on the top 3 systemic constraints (survey or workshop outcome)
- Time from VSM exercise to first experiment targeting the identified constraint

#### DORA Metrics Impact

Work visibility improves all four DORA metrics by making the root causes of performance problems visible. **Change Lead Time** is directly improved when teams can see and act on wait times in the delivery flow. **Deployment Frequency** increases when deployment bottlenecks are identified and removed. Recovery VSM work targets **Failed Deployment Recovery Time** and **Change Fail Rate** specifically.

#### Cost Savings Connection

VSM's ROI comes from targeting improvement investments accurately. Without visibility, teams improve randomly — investing in capabilities that may not address the actual bottleneck. The DORA transformation guide documents multiple cases where organizations invested heavily in one area (e.g., deployment automation) while the actual constraint was elsewhere (e.g., code review latency). VSM ensures that improvement investments are directed at the highest-leverage constraint, maximizing return per dollar of improvement investment.

#### Related Capabilities

- Monitoring and Observability
- Customer Feedback
- Team Experimentation
- Service Reliability

**Source:** [Work Visibility in Value Stream](https://dora.dev/capabilities/work-visibility-in-value-stream/)

---

### Working in Small Batches

Working in small batches is the practice of breaking work into the smallest units that can be independently developed, tested, and delivered to users, with each unit completing the full delivery pipeline before the next begins. It is the operational principle that makes continuous delivery possible and risk manageable.

#### Key Takeaways

- DORA research identifies working in small batches as one of the most powerful practices for improving both delivery performance and organizational learning.
- The 2025 DORA data found that working in small batches has a net-positive impact on product performance and reduces AI-related friction. Small batches contain AI-generated changes and make them reviewable; large batches of AI-generated code are harder to validate and more likely to introduce subtle failures.
- Small batches accelerate learning: each deployment is a learning opportunity, and more deployments mean more feedback cycles.
- The common objection — "our changes are too big to batch" — is usually a symptom of architecture coupling rather than an inherent constraint. Feature flags, strangler fig patterns, and branch-by-abstraction are techniques for enabling small batches in large systems.
- Small batches reduce blast radius: when a failure occurs, the recent change set is small and easily identifiable, dramatically compressing time-to-identification in root cause analysis.

#### How to Measure

- Average commit size (lines of code per commit)
- Average feature branch lifetime
- % of user stories completed within a single sprint/iteration
- Mean time to identify the commit responsible for a production regression

#### DORA Metrics Impact

Working in small batches directly improves **Deployment Frequency** by making each deployment smaller and less risky. It improves **Change Lead Time** by reducing the review and approval burden on each change. It reduces **Change Fail Rate** and **Failed Deployment Recovery Time** by making failures easier to isolate and roll back.

#### Cost Savings Connection

Small batches reduce rework cost through two mechanisms: first, they limit the cost of a mistake to the batch size rather than the full release; second, they surface integration problems faster, when they are cheaper to fix. DORA's rework formula captures both: the % of time on unnecessary rework decreases as batch size decreases, because problems are caught and fixed at the smallest possible scale. For organizations doing large, infrequent releases, moving to small frequent batches can be one of the highest-leverage rework reduction investments available.

#### Related Capabilities

- Trunk-Based Development
- Continuous Integration
- Team Experimentation
- Loosely Coupled Teams

**Source:** [Working in Small Batches](https://dora.dev/capabilities/working-in-small-batches/)

---

## Further Reading

The following resources were used to compile and validate this guide and provide important context for applying DORA in practice:

- [DORA Core Model](https://dora.dev/research) — The foundational research and capability catalog
- [DORA Quick Check](https://dora.dev/quickcheck/) — Baseline your team's current performance
- [2025 State of AI-Assisted Software Development](https://dora.dev/research/2025/dora-report/) — The DORA AI research report with team profiles, AI capabilities model, and benchmark data
- [The ROI of DevOps Transformation](https://dora.dev/research/2020/) — Framework for calculating business value from DORA improvement (rework cost, reinvestment value, downtime cost)
- [Value Stream Mapping for Software Delivery](https://dora.dev/guides/value-stream-management/) — Step-by-step guide to VSM, outcome mapping, and the two value streams
- [How to Transform Your Organization](https://dora.dev/guides/how-to-transform/) — Communities of practice, PDCA, iterative change, and common transformation pitfalls
- [How to Empower Software Delivery Teams as a Business Leader](https://dora.dev/guides/how-to-empower-software-delivery-teams/) — Leadership-level guidance on using DORA metrics across the organizational hierarchy
- [How to Enable Teams to Innovate with Generative AI](https://dora.dev/guides/how-to-innovate-with-generative-ai/) — DORA's strategic framework for AI adoption
- [DORA Community of Practice](https://dora.community/) — Peer learning community for DORA practitioners

---

*Last updated: April 2026. This guide reflects DORA research through the 2025 State of DevOps Report cycle.*

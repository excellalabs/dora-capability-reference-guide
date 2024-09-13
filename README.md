# DORA Capability Reference Guide

The DevOps Research and Assessment (DORA) is a long-running, academically rigorous research investigation. Using behavioral science, the researchers connect software delivery methods to organizational goals and personal well-being. Dora is a compilation of competencies that they have proven to drive organizational performance and well-being.

[DORA Core](https://dora.dev/research/)

## Before Reading

This guide is a snapshot of what's available in the [DORA Capabilities](https://dora.dev/devops-capabilities/) and is meant to serve as a starting point. Some of the information below is a direct copy from the site, and some is a condensed version. Each capability page on the DORA site also provides additional context and supporting links.

**NOTE: This guide only contains the the core competencies. The non-core competencies are in progress!**

Good luck, and have fun!

## DORA Core Competencies

### Code Maintainability

It should be easy to change a code base, which should rarely break when changing the code. Teams should use tooling that supports them to incorporate best practices and leverage tools like SonarQube to eliminate code smells, bugs, and other maintainability issues. If there is a production incident it should be quick to propose changes to patch your code base. The code should also be accessible, meaning it's easy to find and refactor when necessary. This can be measured as a component of the lead time for a change to make it into the code base. Teams should focus on how they are managing their technical and design debt, how they're managing changes (change impact), and how they're managing dependencies and patching. Avoid emergency bypass processes! Your change process should be fast and efficient enough to be effective in the case of an emergency.

#### Ways To Measure Code Maintainability

1. Percentage of the organization's code base that is searchable.
1. Median lead time to change a part of the codebase you can't access.
1. Percentage of code is duplicated or unused.
1. Percentage of libraries for a service that are outdated and the time to upgrade.


[Link](https://dora.dev/devops-capabilities/technical/code-maintainability/)

### Continuous Delivery

Do not confuse or conflate with this more deployments or continuous deployments. This is the ability to release any change, even during business hours, without impacting users. Continuous delivery is an important goal for teams even if they aren't doing continuous deployments. This competency is the end state of several of the other DORA competencies. Continuous delivery relies on other core DORA competencies to help make it a reality. A culture and team capable of continuous delivery improves software delivery performance, system availability, burnout, and disruptive deployments. It also improves psychological safety for teams. 

These are key components of continuous delivery:

* Test Automation
* Deployment Automation
* Trunk-based Development
* Shifting Left On Security
* Loosely Coupled Teams
* Empowering Teams To Choose Tools
* Continuous Integration
* Continuous Testing
* Version Control
* Test Data Management
* Monitoring & Observability
* Proactive Notifications
* Database Change Management
* Code Maintainability

A common pitfall is doing your current process more frequently. Continuous delivery usually involves a lot of change across the entire process. To avoid the risks of bad implementation, complete a value stream mapping exercise to discover bottlenecks. Consider the process for each change and measure the total time for the change to go from version control to production. Measuring time takes on two facets:

1. The actual elapsed time and the development time involved in producing a change.
1. The percentage of time that work is sent back for changes.

This will help you find where your process is lacking. Prioritize work that supports the future state of the value streams. Progress for continuous delivery is reflected in short lead times for changes, low change failure rates, low downtime, and high-quality release frequency.

#### Ways To Measure Continuous Delivery

1. Short lead times for both regular and emergency changes.
1. The same process is used for both regular and emergency changes.
1. Short time to restore service during an outage or degradation.
1. Release frequencies that ensure high-priority features and bug fixes are released promptly.

[Link](https://dora.dev/devops-capabilities/technical/continuous-delivery/)

### Continuous Integration

The practice of continuous integration addresses problems of unintended consequences from changes to a code base. By creating rapid feedback loops through small batch work you're improving your software development delivery and producing high-quality software. Continuous integration means that your developers are integrating their work at regular intervals. Teams perform better when they integrate sooner, and that developer's work doesn't vary significantly from the trunk. Each commit should trigger a build of the software, and each commit should trigger quickly executing tests that prove the software is working. Three things are critical to starting continuous integration:

- Automated Build Process
- Automated Testing Suite
- A CI System that runs the build and automated tests on every check-in

Additionally, practicing trunk-based development and agreeing that broken builds are top priorities are two facets of the success of continuous integration. Continuous integration does not mean you will complete features faster but it decreases the feedback loop duration to get changes into production.

#### Ways To Measure Continuous Integration

1. The percentage of code commits resulting in a build without manual intervention.
1. The percentage of code commits that have automated tests being run without manual intervention.
1. The availability of builds to testers, where applicable.
1. The percentage of tests that provide feedback to developers available within a day.
1. The time it takes to fix a broken build.

[Link](https://dora.dev/devops-capabilities/technical/continuous-integration/)

### Database Change Management

Database changes are often a source of risk and delay. Integrating database work into your software delivery helps build continuous delivery. Teams that perform well store their database changes as scripts in version control and effectively communicate changes across the team. When everyone has visibility into the progress of database changes you will shift the review to the left to alleviate downstream issues. To keep visibility high, implement these two practices:

- Keep all database changes in version control along with application code
- Use a tool that records which changes have been run against which application environments

Continuous delivery aims to eliminate database downtime and there are several strategies you can employ to prevent that. Every change should be tested against production-like data or a mirror of your production environment. This helps catch issues before they reach end users. Teams should also not keep database changes siloed. Communication and having planned strategies for database changes are paramount to this competency.

#### Ways To Measure Database Change Management
1. The percentage of failed changes in which database changes were a contributing factor.
1. The cost of time and team member hours that having downtime for a database causes.
1. The number of database changes that are fully automated vs. database changes that require manual intervention.

[Link](https://dora.dev/devops-capabilities/technical/database-change-management/)

### Deployment Automation

This enabled you to deploy your software to any environment with ease. Your deployment packages need to be created by a CI pipeline, scripts exist to configure environments and perform deployment activities, and you should have environment-specific configuration information. Scripts and configuration information should be stored in version control, and packages should be downloaded from an artifact repository like Nexus. Best practices for deployment automation include:

- Every environment using the same deployment process such that the deployment process is tested many times before going to production
- Anyone with the necessary credentials can deploy any version of any artifact to any environment on demand.
- Keep packages consistent between environments.
- Make it possible to recreate the state of any environment from version control.

The common pitfalls when engaging in deployment automation are complexity, dependencies, manual processes, and poor cross-team collaboration. If you automate a complex and fragile process, it will lead to a fragile automated process. Keep the steps of your deployment idempotent and the deployment order of services independent. Tightly coupled services that have to be deployed together in a certain order introduce complexity and dependency into automated deployments. Every team and service uses the same deployment process to reduce inconsistencies and errors because the process is reliable and repeatable.

#### Ways To Measure Deployment Automation

1. Count the number of manual steps in your deployment process and work to reduce those steps systematically.
1. Gather the percentage of automated steps in the total number of steps and increase that ratio.
1. Determine and track time spent on delays in the deployment pipeline.

[Link](https://dora.dev/devops-capabilities/technical/deployment-automation/)

### Empowering Teams To Choose Tools

Empowering teams to have a choice in their tooling contributes to better continuous delivery and higher software delivery performance because they're able to select tools that benefit them the most. This is not meant to give free rein to select any tool at a whim but to empower and encourage developers to make wise tooling choices. Establish a cross-team baseline for a large and diverse set of tools (such as programming languages used), that you already support or are critical to the business. Review the in-use tools periodically and evaluate these tools' effectiveness. Create a process for deviating from that base toolset. Document the new technology used and why it was selected. Teams should be encouraged to experiment with new tools and emerging technologies because they promote innovation. Regularly communicate the progress or lessons learned by using or adopting a new tool.

[Link](https://dora.dev/devops-capabilities/technical/teams-empowered-to-choose-tools/)

### Flexible Infrastructure

Many organizations seek flexible infrastructure in the form of cloud computing. The US National Institute of Standards and Technologies defines five essential characteristics of cloud computing:

1. On-demand self-service - Provisioning your resources without interaction from the provider.
1. Broad network access - Capabilities can be accessed through diverse platforms.
1. Resource pooling - Provide resources that are pooled in a multi-tenant model.
1. Rapid elasticity - Capabilities can be elastically provisioned and scaled.
1. Measured service - Systems automatically control, optimize, and report resource use.

Many teams that claim to have adopted cloud practices have not met all five of these characteristics. High-performing teams were more likely to have met all of those characteristics. Without having these, many teams fail to reap the rewards of having a cloud-first architecture. Moving infrastructure to the cloud requires a rearchitecting of delivery practices.

Developers should be empowered to provision the infrastructure they need with streamlined and disciplined change management. Infrastructure as code allows teams to manage these changes and apply information security controls. Additionally, having a plan to move from a fixed-cost structure to a variable one helps prevent cloud costs from accidentally running rampant. This requires change at all levels in an organization and alignment from the stakeholders of the cloud infrastructure. Teams should be moving to modern site reliability engineering (SRE) practices through this paradigm shift.

#### Ways To Measure Flexible Infrastructure

1. Consider what benefits you hope to gain from implementing cloud infrastructure, and then measure how well those benefits are realized.
1. Track how your infrastructure is meeting the five characteristics defined by NIST.
1. Measure the proportion of services managed through automated cloud provisioning vs. manual provisioning.

[Link](https://dora.dev/devops-capabilities/technical/flexible-infrastructure/)

### Monitoring And Observability

Monitoring is the solution that allows teams to watch and understand the state of their systems. Observability is the solution that allows a team to debug their system actively. Using both of these, teams should be able to report on the overall health of their systems, the tooling to diagnose issues reported by the system or the customer, and the tooling to find information about unknown items. Monitors and observability solutions are meant to provide leading indicators of an outage or degradation, detect outages, detect unauthorized access, identify long-term trends for capacity planning, and expose unintended consequences. These practices ideally reduce your time to recover from an outage and need to be actionable and understood by your team.

The two high-level ways of looking at a system are Blackbox and Whitebox monitoring.

#### Blackbox Monitoring

In this system, input is sent to a system to be treated like a customer would interact with your system in a sampling-based method. You would use tooling to make synthetic requests to your system in a somewhat random selection. Govern this process with a scheduling system and ensure these inputs are made at a sufficient rate to gain confidence in their sampling. This method should also have a validation engine that helps determine a pass or fail state for a given probe.

#### Whitebox Monitoring

These are your metrics, logs, and traces created by your system. In Whitebox monitoring, your system is sending signals about its health and interactions to be recorded.

To use a monitoring system, your code must be exposed or instrumented to allow its workings to become observable. This might require the developers to write additional code to help expose the inner state of the application.

Distributed systems will have their monitoring in many places and it's important to be able to view them all together at once. When you working with this kind of architecture you need to be able to see everything together for a full picture.

Something to consider is the computational requirements required for generating stats and aggregated data when you have many points of data from monitoring and observability. The team must consider the cardinality and the dimensionality of the data as the resource requirements to aggregate your metrics and logs can increase drastically.

Learn from outages and mistakes with well-documented corrective actions. Additionally, it's important that the monitoring can be updated quickly especially when action items from a postmortem are identified. As such your monitoring capabilities should be in version control and owned by the whole team. Every person needs to understand and be able to update their observability and monitoring. A common pitfall is to try and enumerate all possible error conditions with a corresponding alert. Focus on symptom-based alerting which is when a user-facing symptom is visible or predicted to arise soon. Consider how your alerts are delivered, and ensure they have actionable items. If a team member is constantly receiving alerts they can do nothing about, they will ignore them. Ensure alerts are easy to understand and have steps to correct issues where applicable.

#### Ways To Measure Monitoring & Observability

1. Number of pull requests or changes per week made to the monitoring configuration.
1. Percentage of alerts that are handled at night. Regular night-time alerts can lead to fatigue and burnout.
1. Alerts are evenly distributed across teams.
1. Number of alerts that are not actionable or false alarms. Work to minimize these.
1. Number of failures that happen without alerting or untimely alerting. Work to minimize these.
1. Number of alerts created per week.
1. Percentage of alerts acknowledge within an agreed deadline.
1. Percentage of alerts that are silenced and how long they are silenced for. Work to minimize the amount of silencing.
1. Percentage of alerts where an action could not be immediately taken either due to inability to understand or due to a known issue.
1. The amount of time it takes to resolve an issue reported by an alert.

[Link](https://dora.dev/devops-capabilities/technical/monitoring-and-observability/)

### Test Automation

Fast feedback is a key component of building quality software and relying on manual testing to verify changes slows this process down. Automating tests helps reduce the feedback loop for developers and gives them confidence that the software will work once changes have been made. Teams should create and curate a suite of reliable and fast tests that are run against code every time a commit is made. If manual testing is needed, add these steps into the development cycle and don't rely on doing it in handed-off phases.

Two types of testing are important to make a part of this process are unit tests and acceptance tests.

#### Unit Tests

Test items in small pieces and isolation to ensure their code behaves as designed. Developers should use Test Driven Development to help them build testable software.

#### Acceptance Tests

Test against a running application or with external dependencies mocked to ensure that regressions haven't been introduced and a higher level of functionality is still operational. A good example is testing that verifies a user story works without introducing regressions.

Teams should avoid having test suites that are frequently in a broken state and writing code that is hard to test. The harder something is to test the harder it is to maintain. Teams should also regularly curate and prune their test suites. As good evolves and new features are implemented, it behooves the developers to ensure they're updating and reorganizing tests such that operability is maintained while avoiding growing the number of tests. Tests should always be quick to execute. When a test suite passes, the team should be confident that the software is releasable to production.

Do not tolerate [Flaky Tests](https://testing.googleblog.com/2016/05/flaky-tests-at-google-and-how-we.html)

#### Ways To Measure Test Automation

1. Percentage of tests written by the developers. The goal is that all tests are maintained by the developers.
1. Number of bugs found in user acceptance testing over time.
1. Time spent fixing acceptance test failures.
1. Percentage of unit tests that are meaningful for a real defect and which are poorly coded.
1. Tests run on every pipeline trigger. This is more of a pass/fail than a number.

[Link](https://dora.dev/devops-capabilities/technical/test-automation/)

### Test Data Management

Over-reliance on data defined outside of the test scope can make your tests brittle and hard to maintain. You need to manage how your tests get and use data strategically. The core principles of managing are:

- Adequate test data is available to run fully automated test suites
- Test data for automated test suites can be acquired on demand
- Test data doesn’t limit or constrain the automated tests that teams can run

Unit tests should not depend on data or external state to run, and test data should represent a sample of a sanitized production scenario, not be a copy of the production database. Test data also requires maintenance as features get added and the database evolves, so using it sparingly will decrease the time spent developing test cases. Teams should favor unit tests and use a traditional testing pyramid to keep this overhead low and keep execution quick. When test data is used, make sure it's isolated and only mutable by the tests they pertain to.

#### Ways To Measure Test Data Management
1. Track how much time developers and testers spend managing and manipulating data for test suites.
1. The frequency that test data sets are available, refreshed, or accessed.
1. The number of tests that can be run without the need to acquire additional test data.

[Link](https://dora.dev/devops-capabilities/technical/test-data-management/)

### Trunk-based Development

This is the practice of working in small batches that are continuously merged back to the default branch a.k.a. the trunk. In this workflow, branches are meant to be short-lived and limited scope. This approach does not require feature branches, once code is merged into the trunk it is considered ready for production. There might be instances, like hotfixes, where you'd want to make a release that has cherry-picked commits, but it should be merged back into the trunk as soon as possible. Bigger and longer branches typically result in a longer delivery time and more code regressions. Having an overly heavy-handed review process, asynchronous code reviews or a lack of automated testing are common pitfalls to this approach as they slow down development and delivery. One thing that helps with adoptions is to do it in waves and have folks attempt trunk-based development in batches with specific repos, then migrate the approach to any additional code bases. Team members that engage with trunk-based should then mentor other team members to guide them through the transition.

#### Ways To Measure Trunk-Based Development

1. Measure how many branches are active in a repository and try to not have more than three active branches at a time.
1. Measure the frequency and duration of code freezes and work toward eliminating them.
1. Measure how frequently work is being merged into the trunk
1. Measure the average time it takes to approve pull requests and work on reducing it.

[Link](https://dora.dev/devops-capabilities/technical/trunk-based-development/)

### Version Control

Version control enables teams to have traceability on code changes and version history to restore state to their code bases. A version control mechanism where all artifacts are recorded enables teams to have faster disaster recovery and auditability. It also allows for reduced time to implement changes. Version control should extend past code and encompass any artifact that your team generates, including documentation or standing up a production environment from a snapshot. The goal is to ensure that anything that teams need to be restored has a history where each state is reproducible.

#### Ways To Measure Version Control
1. The percentage of code that is stored in version control.
1. The time it takes for developers to recover code from version control.
1. Percentage of configurations in version control.
1. The time it takes for developers to reconfigure systems through version control.

[Link](https://dora.dev/devops-capabilities/technical/version-control/)

### Documentation Quality

Internal documentation has a clear link to organizational performance. DORA has eight metrics to assess documentation quality. A few of them are clarity, findability, and reliability. Documentation needs to be actively maintained. Have your team learn what it takes to make high-quality and usable documentation.

[Link](https://dora.dev/devops-capabilities/process/documentation-quality/)

### Loosely Coupled Teams

Architecture is a predictor for achieving continuous delivery. Architectural practices that drive successful outcomes:

- Making large-scale changes to the design of systems without the permission of somebody outside of their team and without dependency on another team.
- Work is completed without needing extensive communication outside of the team.
- Products or services can be deployed on demand, independent of other services.
- Not requiring an integrated test environment and being able to perform testing on demand.
- Downtime is negligible.

Organizations are biased toward designing architecture that mimics their communication structure. To counteract tightly coupled Architecture, organizations can use the [Inverse Conway Maneuver](https://medium.com/better-practices/how-to-dissolve-communication-barriers-in-your-api-development-organization-3347179b4ecc) to avoid designing a system that mirrors an organization's communication style. With tightly coupled architecture, small changes can result in cascading failures, leading to extensive change management processes. Architecture should be able to quickly and easily evolve to meet the necessities of the organization over time.

Having to release many services together, or "Big-Bang" deployments are cumbersome and takes excessive time to release. This is worsened when you also must integrate interdependent changes from hundreds or thousands of other developers. Additionally, testing these in environments that do not mirror production reduces the value of the testing. All of this becomes an exceptionally long lead time for changes. Focus on an architecture that enables small teams of developers to independently implement, test, and deploy code into production safely and quickly.

A pattern that can be adopted to help improve migrating architecture is the strangler fig application. In this pattern begin replacing integrated application services one at a time with loosely coupled services. These services can still feed into the tightly coupled architecture until you reach a tipping point and can decouple core services. when deciding to make a piece of functionality into a service, consider the following traits:

- The service implements a single business function or capability.
- The service performs its function with minimal interaction with other services.
- The service can be scaled, built, and deployed independently from other services.
- The service communicates with other services using lightweight methods such as HTTP endpoints or a message bus.
- The service can be implemented with different tools, programming languages, data stores, and so on.

#### Ways To Measure Loosely Couple Architecture

1. As services and products become decoupled, deployment frequency should increase. This should be measured on the cadence of deployment rather than deployment count.
1. Measure the time it takes to detect and recover from problems and the time it takes for those problems to be resolved in a production environment.

[Link](https://dora.dev/capabilities/loosely-coupled-teams/)

### Pervasive Security

By integrating security into daily work, and as early as possible, teams can build more secure systems and take a less reactionary stance to security issues. Defects involving security, performance, and availability are the most resource-consuming issues and require hard-to-implement changes. By implementing security as early as possible, high-performing teams can mitigate these kinds of issues. Teams also eliminate the need for post-inspection which helps with continuous delivery. Whoever is in charge of your security needs to be included in the design phase of building software. This is the best way to catch issues early on and ensure that your application has sufficient automated testing. By automating critical tests, you also reduce the manual aspect of security inspection. It's important to have an understanding of common security vulnerabilities, understand the principle of least privilege, and engage with your security team.

#### Ways To Measure Shifting Left On Security

1. The percentage of features that undergo security review early in the development process.
1. The time a security review took and added to the development process.
1. The involvement of InfoSec in the development lifecycle (design, development, test, and release).
1. The involvement of InfoSec in writing automated tests. Automated tests should sufficiently cover security concerns.
1. The involvement of InfoSec and the use of preapproved libraries and packages. Teams should strive to use 100% preapproved by InfoSec tools.

[Link](https://dora.dev/capabilities/pervasive-security/)

### Streamlining Change Approval

Research by DORA from the 2019 State of DevOps Report finds that change approvals are best implemented through peer review during the development process and supplemented by automation to correct bad changes early in the software delivery life cycle. Continuous testing, continuous integration, and comprehensive monitoring and observability provide that automated detection. Heavy-weight approaches to change approval slow down the delivery process and encourage the release of larger work batches less frequently, which brings an increased risk of increasing change failure rate. Developers should be able to get automated and peer review feedback quickly, and adjustments should be able to be made quickly. Things like a Change Approval Board (CAB) still have usefulness in facilitating notifications and coordination, and weighing in on important business trade-off decisions like time-to-mark and business risk. Code review should be done by practitioners and automated methods to keep management focused on strategic work.  Relying on a centralized CAB board to catch errors and approve changes can introduce delay and error. Teams should focus on applying continuous improvement not default to adding more processes to manage production instability.

While moving away from traditional, formal change management processes is the ultimate goal, having a well-defined and understood process is also beneficial. If your team knows how to get changes reliably approved and deployed, it drives higher performance.

#### Ways To Improve Change Approval 

- Peer review-based process for individual changes enforced at code check-in time
- Automated discovery of vulnerabilities, regressions, and performance issues.
- Identify and shift change approval bottlenecks to the development platform.
- Implement information security controls at the platform and infrastructure layer rather than a manual review as part of the software delivery process.

#### Ways To Measure Change Approval

1. Measure the percentage of approvals that do (or do not) require a manual change to be promoted to production.
1. Measure the time changes spend waiting for approval from external bodies.
1. Measure the number or proportion of changes that require approval from external bodies.

[Link](https://dora.dev/devops-capabilities/process/streamlining-change-approval/)

### Generative Organizational Culture

An organizational culture that is high-trust and emphasizes information flow is predictive of performance at all levels.

#### Generative Qualities

* Performance Oriented 
* High Cooperation
* Trained Messengers
* Shared Risks
* Bridging Encouraged
* Failure Leads To Inquiry
* Novelty Implemented

To begin implementing this kind of culture, you need to change how people work. Create cross-functional teams so that everyone has a shared responsibility for the product. Break down silo's between your team members. While not every member will take on every responsibility, having a shared understanding of all roles helps teams bridge communication gaps. Treat bad news as a learning opportunity and keep it blameless. Blaming individuals creates a negative culture, and instead, you should focus on how to make your product resilient to the types of failures you experienced. Finally, there should be a focus and encouragement for team members to bring novel ideas to test out. A few pitfalls to this are ignoring the importance of culture, punishing bad news, keeping local team cultures, and not encouraging novelty. 

When implementing a generative culture, you should focus on:

* Messengers are not punished for bad news
* Information is actively sought
* Cross-functionality is encouraged and rewarded
* New ideas are welcomed

[Link](https://dora.dev/devops-capabilities/cultural/generative-organizational-culture/)

### Well-being

A reflection of people's happiness and job satisfaction. There are two areas that DORA has focused on to describe how development practices impact people's well-being.

#### Deployment Pain

A measure of the fear and anxiety that engineers and technical staff feel when it's time to make a production release. This is also measured by how disruptive versus easy it is to deploy code to production. Delivery performance drops when it's hard or painful to release production code.

#### Rework

This is another measure by which we can tell when quality is implemented into the product from the start. To conceptualize how teams spend their time we can think of it as proactive and new work or reactive and unplanned work (rework). Rework is fixing things that weren't done right the first time. High-performing teams spend more time on proactive work because they have adopted the practices of building quality from the start and reacting less.

People who suffer from constantly reacting might experience burnout. Burnout can arise from six organizational factors:

- Work overload
- Lack of control
- Insufficient rewards
- Absence of fairness
- Breakdown of community
- Value conflicts

Most organizations try to fix the person rather than addressing issues with the organization which is much less successful.

[Link](https://dora.dev/devops-capabilities/cultural/well-being/)

## DORA Other Competencies

### Customer Feedback

Validating your features is critical to team success and well-being. Customer feedback is part of a wider group of capabilities comprise of visibility of work in the value stream, small batch work, and team experimentation. When these capabilities are applied together they help prediec software delivery performance and organizational performance. Teams should actively seek customer feedback and use it to drive their features.

It's important to derive success metrics for your product based on how your customers interact with it. The metrics should be suitable to the product you're building and be a key driver of the product strategy. It doesn't matter if your product is client-facing or for internal teams, the same philosophy applie. Early and frequent engagement with the people who use your product is paramount to ensure successful software delivery. Otherwise you might be building tools or features that nobody uses which can cause burnout and wasted resources. Increased customer engagement also helps align the team to organizational goals and values.

One big issue with not gathering customer feedback is not understanding the problem customers are facing. Teams might even ignore inconvenient feedback and label it as scope creep. A team wants to keep the scope of their work to the mimnum that's required to solve the problem, but not understanding the problem can lead to a failed product. Teams need to be able to act on the feedback and be able to iterate or pivot when their plans don't align with customer needs.

User Experience (UX) designers are extremely helpful in gathering feedback and ensuring the team is solving real customer problems. UX is about every experience a user has when they interact with the product and can help teams align their plans with real cusomter needs rather than assumed ones.

#### Ways To Improve Customer Feedback

- Define metrics that measure customer satisfaction
- Validate features before building them with user research and prototypes
- Changes to features should be drive by your customers
- Activey gather and act on customer feedback

[Link](https://dora.dev/capabilities/customer-feedback/)

### Monitoring Systems To Inform Business Decisions

When properly implemented, monitoring gives you insights into your systems and gives you rapid feedback for early problem detection. These help you communicate information about your systems to other parts of the business. By sharing knowledge and identifing learnings, you can share these across your organizations to improve systems. Collection data from key areas like performance and infrastructure, and using those to make business decisions are paramount to this capability. The data being shared across the business should be relevant, timely, accurate, and easy to understand. Providing context to your data is also critical to help stakeholders understand the data being shared. Make use of the Monitoring and Observability capability to help drive useful and actionable alerts that give you insight into your systems. 

#### Ways To Improve Monitoring Systems To Inform Business Decisions

- Collect data from key areas throughout the value chain. Do a gap analysis on gathered data to help ensure the data is right for your organization.
- Ensure the data is available, shared, and used to guide decisions.

[Link](https://dora.dev/capabilities/monitoring-systems/)

### Proactive Failure Notification

The practice of generating notifications from thresholds rather than after a problem has occurred in a given system. With this approach, it's possible to identify and resolve issues before they impact your end users. According to DORA, teams that have proactive notifications can diagnose and solve problems quickly. Notifications should be generated using specific alerting rules based on thresholds. Thresholds for these rules should be predictive and not based on arbitrary values. If you have have known values that cause user impact, your thresholds should start alarming once you're within 20% of that threshold. Incident post-mortems can also help you determine these metrics and thresholds. Once you have a plan in place, actively review and adjust your notification strategy to avoid unactionable notifications.

#### Ways To Improve Failure Notification

- Configuring alerts in logging and monitoring systems to appropriate levels.
- Configuring alerts to make sure they notify people and teams who can actually fix the problem.
- Proactively monitoring system health based on rate of change warnings.
- Ensure that only relevant alerts are occurring.

[Link](https://dora.dev/capabilities/proactive-failure-notification/)

### Team Experimentation

For an organization to fully benefit from modern software development techniques, teams must be able to experiment with real users to achieve agreed upon business outcomes. This allows developers to quickly prototyp and test ideas as they learn more about the problem, and design solutions. This practice helps teams ship features that add value to the organization frequently. Team members should be able to work on new ideas without having to get external permission, they should be able to update specifications during development, and the ability to make changes to stories without having to get external approval. Providing treams with information and context lets themmake informed decisions about the right work to do. It's up the individual performing the work to fill in details and update user stories when they deem it appropriate. Developer's shoudln't be handed strict, unchangeable requirements, but rather leaned on to experiment to uncover the best solution.

#### Ways To Improve Team Experimentation

- Hold regular hackathons to let teams experiment with new tools and technologies.
- Encourages teams to iterate on and conitnually improve solutions.
- Allow developers and operators to talk to and observe customers.

### Visibility Of Work In The Value Stream

This represents the extent to which teams have a good understand of how their work flow from business requirements all the way to customers. Teams that are proficient at value visibiity are able to easily see the visual flow of their work through the flow, and information about the flow is readily made readily available. A useful technique to develop this is value stream mapping. Gather stakeholders from every part of the product development lifecycle and create a diagram of process blogs. Record in each process block the team that manages that process, the steps they use to accomplish that process, the time it takes to complete the process, and the percentage of items that hit a stage without requiring rework. Looks for prcoesses that block or produce low quality work, or processes that have a long lead time for completion. Work with stakeholder to identify what a future value stream might look like as well. Teams should be evaluating the current state and future state every six months to a year.

When putting together a value stream, remember that not one single person or team has great insight into the whole value stream. It's paramount to include people across the entire stream for feedback. This will also help you map the entire stream without missing any steps. Failure to map a certain step can lead to local optimazation but missed opportunities to improve the whole process. Focus on areas that are actual bottlenecks for immprovement first, even if all the steps can be improved. The people inovled with the value mapping should also have the power to institute changes to help eliminate bottlenecks.

#### Ways To Improve Work Visibility

- Provide tools for visualizing and recording workflow.
- Create a value stream map.
- Share artifacts or otherwise make them widely available.

[Link](https://dora.dev/capabilities/work-visibility-in-value-stream/)

### Visual Management

Visual management board can create a share understanding of where the team is, and can help identify and remove obstacles. This can be cards, storyboards, Kanban boards, dashboards, or even pipeline monitors. The goal is to be able to visual the status of systems and work. Visual management works well with work in progress limits and can contribute to high levels of deliveyr performance. It's important to involve the team with metric selection and definiton if you're creating boards that display metrics. Displays should be simple and provide information that is actionable. As time goes on, the displays should evolve to address issues the team is facing in the present, and teams should be empowered to fix underlying issues, not just sympotoms.

#### Ways To Improve Visual Management

- Reflect information that the team cares about and will acton.
- Make data easy to understand.
- Give the team information that is relevant to their work.
- Displays are updated as part of daily work.

### Work In Process Limits

DORA research shoes that WIP limits help drive improvements in software delivery, especially when combined with visual displays and monitoring driven feedback loops. Assigning a person to work on multiple items at a time causes the work on both tickets to take longer, and causes team burnout. The best way to start is to use a storyboard (JIRA, or other) to visualize the columns of the workstream. Each column should specify a WIP limit which defines how many active work items can be in a given column at any time. The WIP capacity will vary by team, but a good esitmate is that the WIP limit should be 50-60% of your team size. If you have eight developers, your WIP limit for active development tickets should be closer to four or five. The limits should be adhered to, meaning no card moves from one column to the next if it breaks the WIP limit. This can result in team members sitting idle for a time, but the response to this is for those team members to begin identifying places in your process to be improved to reduce time spent idling. The point of imposing WIP limits is to expose problems in the system so they can be addressed.

#### Ways To Improve Work In Process Limits

- Make all your work visible to avoid miscalculating capacity
- Set WIP limits that match your teams capacity for work. People shouldn't work on multiple tasks at a time and account for activities such as production support.
- Set recurring meetings for stakeholders to prioritize work in columns where developers pull from.
- Improve work processes and increase flow so that starting and completing work has low variability and teams aren't sitting idle.

### Working In Small Batches

Working in small batches is an essential principle in any discipline where feedback loops are important, and is a necessary condition for trunk-based development and continuous integration. Adoping this practice allows you to rapidly test hypotheses about whether a particular improvement is likely to have the effect you want, or course correct to revist assumptions. In traditional phased approaches to software development, handoffs from development to test, or test to IT consist of lengthy and large releases. Getting feedback on changes and features released could take months or weeks. Working in small batches lets your reduce this feedback loop and prevent some of the long term headaches that stem from only validating items in bulk. When planning new features, use the agile concept of the INVEST principle to help understand how to break down work. You can use approaches such as dark launching, which is when a feature has work that's okay to put into production while the feature may not be finished or available to end users. Another approach would be to use feature toggles to hide the feature in production while still merging and promoting code daily. Another example of this is branching by abstraction. For example teams might choose to do a migration between services by allowing both the old and new services to exist in parallel and then migrating older services to new services incrementally. Avoid working in small batches that get regrouped before they're merged into the trunk. Regrouping working in this way delays the feedback on whether the changes have defects, and whther your changes were the right thing to build.

#### Ways To Improve Working In Small Batches

- Work is decompoxed in a way that enables teams to make more frequent production releases.
- Developers are expeirienced in breaking down work into small changes that can be completed in the space of hours, not days.

### Job Satisfaction

Job satisfaction is a predictor of organization performance. Engaged employees drive business value. People do better work when they feel supported by their employers, when they have the tools and resources to perform their jobs, and when they feel their judgement is valued. Dedication to continuous improvement if what sets apart successful companies, and helps with satisfcation. If you're trying to make ogranizational change, don't forget you must make time and resoucres available for the improvements. Transformations are hard and take time, and make things difficult for employees to navigate. Teams that routinely work on making these changes and improving processes are more likely to stay with the company. 

Measuring job satisfaction is hard. The best way is to get people's opinions, but if you're worried that you won't receive accurate answers then that's a signal that something is wrong and should be investigated.

[Link](https://dora.dev/capabilities/job-satisfaction/)

### Learning Culture

### Transformational Leadership

## DORA Key Metrics

Every competency in some way or another feeds into these metrics. Improving any of the core competencies will drive you toward building a high-performing team. As you adopt and utilize more DORA capabilities, you will see how they impact these metrics.

To see how you are doing on delivery performance you can take the [DORA Quick Check](https://dora.dev/quickcheck/)

### Deployment Frequency

**How frequently a team successfully releases to production, e.g., daily, weekly, monthly, yearly.**

### Lead Time For Changes

**The median amount of time for a commit to be deployed into production.**

### Time To Restore Changes

**For a failure, the median amount of time between the deployment that caused the failure and the remediation. The remediation is measured by closing an associated bug/incident report.**

### Change Failure Rate

**The number of failures per the number of deployments. For example, if there are four deployments in a day and one causes a failure, that is a 25% change failure rate.**

Using these metrics, the DORA research was able to group development teams into categories. Those in the highest category were often found to be beating their organization's expectations.

![dora-chart](https://github.com/agriffi10/treasury/assets/30501888/be4fdae6-007a-4b66-98a4-08707ef38a46)

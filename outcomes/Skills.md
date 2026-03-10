# Skills dictionary for IBM Instana Subject Matter Expert (SME)


## APM & Observability Foundations


### S1 - APM Core Concepts (Transactions, Traces, Spans, SLIs/SLOs)

- **What/Why:** Understand end‑to‑end request flows, latency, throughput, error rates, and how they tie to user experience and business outcomes.
- **Prove it:** Walk through a real production incident timeline correlating trace waterfalls to SLI/SLO impacts; show pre/post metrics and remediation steps.



### S2 - The Three Pillars (Metrics, Logs, Traces) + Events

- **What/Why:** Holistic visibility: metrics for trends, logs for detail, traces for causality, and events/changes for context.
- **Prove it:** Present a triage playbook using all three pillars; show a dashboard with correlated metric anomalies, log pivots, and trace exemplars.



### S3 - Service Topology & Dependency Mapping

- **What/Why:** Know how services, data stores, queues, and external APIs relate; crucial for blast‑radius analysis and RCAs.
- **Prove it:** Demonstrate a topology map and explain a specific dependency‑driven latency propagation scenario.



### S4 - SRE & Reliability Practices

- **What/Why:** Error budgets, SLO‑driven alerting, and reducing toil through automation.
- **Prove it:** Provide defined SLOs, error budget policy, and examples of alert reduction/toil elimination over time.




## Instana Platform Expertise (SaaS & Self‑Hosted)


### S5 - Instana Architecture & Components

- **What/Why:** Know Instana agents, collectors, backend, data model, retention, and tenancy; SaaS vs. self‑hosted trade‑offs.
- **Prove it:** Draw the deployment architecture you’ve implemented, including sizing, data retention, and HA/DR considerations (if self‑hosted).



### S6 - Smart Alerts, Dynamic Baselines & Anomaly Detection

- **What/Why:** Reduce noise with context‑aware alerting based on service health, golden signals, and dynamic thresholds.
- **Prove it:** Show alert configurations, baseline learning windows, and historical alert volume before/after tuning.



### S7 - Automatic Discovery & Continuous Profiling

- **What/Why:** Instana auto‑discovers services and dependencies; continuous profiling surfaces code‑level hotspots.
- **Prove it:** Share a profiling session that found a CPU/memory hotspot and the code change that resolved it.



### S8 - Instana Dashboards & Notebooks (Optional)

- **What/Why:** Create consumable, role‑based visualizations for SREs, devs, and execs; documented narratives for incidents.
- **Prove it:** Portfolio of custom dashboards and a post‑incident notebook with embedded traces/metrics/logs.



### S9 - Instana Querying & Analytics

- **What/Why:** Use Instana’s analytics to explore high‑cardinality data, filters, tags, and facets to isolate issues.
- **Prove it:** A recorded walkthrough where you isolate a latency spike to a specific version or endpoint via querying.



### S10 - Change & Release Correlation

- **What/Why:** Overlay deployments/config changes with performance to shorten MTTD/MTTR.
- **Prove it:** Example of a regression pinned to a specific release, with rollback time and MTTR improvement metrics.




## Instrumentation & Data Collection


### S11 - Agent Deployment & Lifecycle (Servers/Containers/Hosts)

- **What/Why:** Install, upgrade, configure agents; validate data integrity and overhead.
- **Prove it:** Automation scripts/Ansible manifests/Helm charts for agent rollout, plus validation queries and overhead stats.



### S12 - Kubernetes/OpenShift Instrumentation

- **What/Why:** Cluster‑wide visibility—nodes, pods, services, ingress, sidecars; cluster health and workload insights.
- **Prove it:** Show a live cluster view, service maps, and HPA/autoscaling impacts correlated with app SLOs.



### S13 Code Auto‑Instrumentation & Manual Instrumentation

- **What/Why:** Use Instana auto‑tracing for common runtimes; add custom spans/attributes for domain‑specific visibility.
- **Prove it:** Code samples adding custom spans/tags and the resulting enriched traces in Instana.



### S14 - OpenTelemetry Interoperability

- **What/Why:** Ingest and correlate OpenTelemetry traces/metrics/logs with Instana.
- **Prove it:** A demo app exporting OTel data, mapped in Instana alongside native instrumentation.



### S15 - Backend & Messaging Visibility

- **What/Why:** Deep instrumentation across HTTP/gRPC, DBs (SQL/NoSQL), caches, queues (Kafka/RabbitMQ), and external APIs.
- **Prove it:** Trace examples that cross DB calls and message queues; show slow query analytics and optimization outcomes.



### S16 - RUM (Real User Monitoring) & Mobile APM

- **What/Why:** Browser/mobile app performance (TTFB, CLS, LCP), session traces, resource waterfalls.
- **Prove it:** RUM dashboard with geographic performance breakdowns and a case study improving LCP or error rates.



### S17 - Synthetic Monitoring

- **What/Why:** Proactive checks of critical journeys and SLIs from multiple locations.
- **Prove it:** Synthetic scripts + failure snapshots, and how they averted an incident by early detection.



### S18 - Logs Ingestion & Correlation

- **What/Why:** Route and correlate logs to spans/services (via parsers, pipelines, and tags).
- **Prove it:** Show log correlation from a span to the exact error log lines; include pipeline/regex/parser config.




## Cloud & Infrastructure Monitoring


### S19 - Cloud Integrations (AWS/Azure/GCP)

- **What/Why:** Collect cloud service metrics (ELB, Lambda, S3, Cosmos, Pub/Sub, etc.) and correlate with app health.
- **Prove it:** Cloud integration setup plus an incident where a cloud service limit/degradation impacted app SLIs.



### S20 - Host/VM/Container/Process Monitoring

- **What/Why:** System health (CPU, memory, disk I/O), container resource contention, noisy neighbors.
- **Prove it:** Dashboards showing host‑to‑pod causality and a capacity fix that eliminated throttling.



### S21 - Network & Edge (Ingress/Service Mesh/CDN)

- **What/Why:** Surface L7 metrics, connection errors, TLS issues; observe service mesh/ingress behavior and latency.
- **Prove it:** Trace segments across ingress/mesh with latency contribution breakdown and resolved network misconfig.




## Alerting, Triage & Root Cause


### S22 - Service Health Models & Golden Signals

- **What/Why:** Design alerts around user‑impacting indicators (latency, errors, saturation).
- **Prove it:** Before/after alert tuning, including reduced false positives and improved page quality.



### S23 - Automated Root‑Cause Hints & Causality

- **What/Why:** Use Instana’s cause detection with topology/context to pinpoint likely origin quickly.
- **Prove it:** RCA documents that reference Instana’s cause indicators with corroborating traces/logs.



### S24 - Runbooks & Incident Playbooks

- **What/Why:** Standardize triage for repeat classes of failures; speed up MTTR.
- **Prove it:** Version‑controlled runbooks with metrics showing MTTR improvements after adoption.



### S25 - Incident Communications & Postmortems (Optional)

- **What/Why:** Clear stakeholder updates; blameless postmortems with actionable follow‑ups.
- **Prove it:** Real postmortems including SLO impact, five‑whys, corrective actions, and ownership.




## Automation, CI/CD & “Observability‑as‑Code”


### S26 - Instana APIs & Automation

- **What/Why:** Use REST APIs/SDKs to manage alerts, dashboards, tags, and configuration at scale.
- **Prove it:** Scripts/CI jobs that auto‑provision dashboards/alerts per service or environment.



### S27 - Tagging/Naming Conventions & Metadata Hygiene

- **What/Why:** Consistent service/version/env tags power accurate filtering, ownership, and analytics.
- **Prove it:** A documented tagging standard and evidence of adoption in service inventory and queries.



### S27 - Shift‑Left in CI/CD (Release Gates)

- **What/Why:** Bake performance checks and canary/feature‑flag signals into pipelines.
- **Prove it:** Pipeline snippets that fail builds on SLI regressions; Instana release markers in traces.



### S28 - Auto‑Remediation & ChatOps

- **What/Why:** Trigger runbooks or rollbacks from alerts; tight integration with Slack/Teams/ITSM.
- **Prove it:** A demo showing alert→bot→runbook execution with guardrails and success verification.




## Performance Engineering & Capacity


### S29 - Load/Stress/Soak Testing with Observability

- **What/Why:** Use Instana to analyze bottlenecks under controlled load; validate optimizations.
- **Prove it:** Test plan + comparison dashboards (baseline vs. after optimizations), with cost/perf deltas.



### S30 - Bottleneck Identification & Optimization

- **What/Why:** DB indexes, N+1 queries, thread pool tuning, connection pools, garbage collection.
- **Prove it:** Before/after traces and profiling sessions tied to specific code/config changes.



### S31 - Capacity Planning & Right‑Sizing

- **What/Why:** Forecast capacity, reduce over‑provisioning without violating SLOs (FinOps synergy).
- **Prove it:** Capacity model and realized savings with SLO adherence (e.g., % infra cost reduced vs. SLO maintained).




## Governance, Security & Compliance


### S32 - RBAC, Tenancy & Access Controls

- **What/Why:** Proper scoping for teams and environments; least privilege and auditability.
- **Prove it:** RBAC matrix and demonstration of scoped dashboards/permissions.



### S33 - PII/Data Handling & Retention Policies

- **What/Why:** Ensure logs and traces comply with privacy regs; configure redaction/sampling.
- **Prove it:** Redaction rules, sampling configs, and audit results validating compliance.



### S34 - Change Management & ITIL Integration

- **What/Why:** Link incidents, problems, and changes with observability context.
- **Prove it:** ITSM tickets enriched with Instana links, plus mean lead time for change and failure rates.




## Multi‑Platform Runtime Expertise


### S35 - Languages & Frameworks

- **What/Why:** Strong working knowledge across Java/.NET/Node.js/Python/Go/Scala/Ruby and common frameworks (Spring, ASP.NET, Express, Django, etc.) to interpret traces.
- **Prove it:** Mixed‑stack trace walkthroughs and fixes across at least two different runtimes.



### S36 - Data Stores & Caches

- **What/Why:** SQL/NoSQL and cache tuning (PostgreSQL, MySQL, MongoDB, Redis, etc.) and their telemetry.
- **Prove it:** A database tuning case (index/query plan) with Instana evidence of improved latency/throughput.



### S37 - Event‑Driven & Streaming

- **What/Why:** Kafka/RabbitMQ streams and consumer lag, partitioning, backpressure visibility.
- **Prove it:** Dashboards tracking consumer lag and remediation changes (e.g., concurrency or partition realignment).




## Ecosystem Integrations


### S38 - Ticketing/On‑Call (Jira/ServiceNow/PagerDuty/Opsgenie)

- **What/Why:** Close loop from detection to response and resolution.
- **Prove it:** Live integration paths, with enrichment and auto‑assignment rules.



### S39 - Collab/Comms (Slack/Teams)

- **What/Why:** Real‑time triage with deep links to Instana artifacts.
- **Prove it:** Incident room transcripts and Instana deep‑links used during an event.



### S40 - Data Export & BI

- **What/Why:** Export or federate metrics for finance/ops dashboards (e.g., cost, business KPIs).
- **Prove it:** Example of Instana‑informed executive scorecard correlating user KPIs with SLOs.




## Migration & Enablement (Optional)


### S41 - APM Migrations (e.g., from Dynatrace/AppDynamics/New Relic) (Optional)

- **What/Why:** Plan data parity, tagging alignment, alert translations, and stakeholder adoption.
- **Prove it:** A migration runbook and a parity matrix showing mapped capabilities and outcome metrics.



### S42 - Developer Enablement & Playbooks (Optional)

- **What/Why:** Scale observability literacy via patterns, templates, and office hours.
- **Prove it:** Training materials, lunch‑and‑learn recordings, and adoption metrics (service coverage %, alert hygiene).



### S43 - Value Realization & ROI (Optional)

- **What/Why:** Tie observability to tangible outcomes (MTTR reduction, change fail rate, infra savings, revenue protection).
- **Prove it:** A value dashboard with trend lines and agreed business KPIs.




## Soft Skills for an Expert (Optional)


### S44 - Clear Communication & Stakeholder Management (Optional)

- **What/Why:** Translate technical insights into business impact; align with product/ops/security.
- **Prove it:** Executive‑level readouts and decision memos from real incidents or performance programs.



### S45 - Prioritization & Pragmatism (Optional)

- **What/Why:** Focus on the 20% of signals that drive 80% of outcomes; avoid tool sprawl.
- **Prove it:** A phased roadmap (90‑day plan) and results from a focused alert‑hygiene initiative.



### S46 - Coaching & Mentoring (Optional)

- **What/Why:** Create a culture where teams self‑serve and self‑debug.
- **Prove it:** Mentorship feedback, improved on‑call effectiveness, and reduced escalations.
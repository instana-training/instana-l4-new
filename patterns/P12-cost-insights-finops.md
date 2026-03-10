# Pattern Card P12 — Cost Insights & FinOps (Instana + Kubecost)

**Module:** M5 — Security & Governance (cross‑cutting with Ops)  
**Version:** March 2026

## Intent

Use Instana’s **native integration with IBM Kubecost** to bring **Kubernetes cost, allocation, efficiency, and savings metrics** directly into the Instana console.  
Correlate cost spikes with deployments, performance regressions, namespace‑level activity, and cluster utilization trends to drive **FinOps‑aligned optimization**.  
[1](https://www.ibm.com/new/announcements/unlocking-peak-kubernetes-performance-and-cost-efficiency-with-ibm-instana-powered-by-ibm-kubecost)[2](https://community.ibm.com/community/user/blogs/chinmayi-panicker/2025/06/02/integrating-kubecost-with-instana-for-comprehensiv)

---

## Prerequisites

- Kubecost **installed in the same Kubernetes cluster** monitored by the Instana agent.  
  Instana uses the **Kubecost REST APIs** to import cost/allocation metrics. [3](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=hosted-integrating-kubecost)
- Instana agent deployed with the **Kubecost sensor** enabled (remote agent or host agent in K8s).
- For Kubecost setups requiring auth: access to a **Kubecost API key**. [3](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=hosted-integrating-kubecost)
- Access to Instana dashboards (Cost tab) and permissions to configure agent sensors and dashboards.

---

## Example scenario

Your Kubernetes workloads run in multiple namespaces. A recent deployment increases CPU requests and triggers higher EKS cloud spend.  
Using the **Instana + Kubecost** integration:

1. You open the **Cost dashboard** in Instana and immediately see the **cluster‑level cost spike**. [1](https://www.ibm.com/new/announcements/unlocking-peak-kubernetes-performance-and-cost-efficiency-with-ibm-instana-powered-by-ibm-kubecost)
2. You drill down by **namespace and workload**, visualizing spend distribution and idle cost. [1](https://www.ibm.com/new/announcements/unlocking-peak-kubernetes-performance-and-cost-efficiency-with-ibm-instana-powered-by-ibm-kubecost)
3. You compare the spike against **release markers** to confirm which deployment correlated with the increase. [4](https://community.ibm.com/community/user/blogs/surabhi-surabhi/2025/02/10/instana-kubecost)
4. You propose a right‑sizing action to reduce request limits or scale configuration.

---

## Build recipe

### 1) Deploy and connect Kubecost

- Deploy Kubecost in the same K8s cluster(s) the Instana agent monitors.  
  Instana supports **Kubecost Foundations (free tier)** and **Kubecost Enterprise**.  
  Foundations allows <250 vCPU and one cluster; Enterprise supports unlimited clusters.  
  [3](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=hosted-integrating-kubecost)
- Provide a Kubecost **Product Key** (for Foundations/Enterprise) so Kubecost can collect resource‑usage metrics.[3](https://www.ibm.com/docs/en/instana-observability/1.0.313?topic=hosted-integrating-kubecost)

### 2) Enable the Instana Kubecost Sensor

Edit the Instana agent config, for example:

```yaml
com.instana.plugin.kubecost:
  remote:
    - url: 'http://<your-kubecost-address>'
      api_key: '<optional-if-auth-enabled>'
  poll_rate: 1800 # recommended default (30 minutes)
  clusters: # optional; omit for dynamic cluster detection
    - 'cluster-one'
```

url: Kubecost endpoint.
api_key: optional, required only if Kubecost enforces authentication.
clusters: list of K8s clusters. Omit for dynamic detection (recommended for enterprise scale). [ibm.com], [community.ibm.com]

3. Validate data in Instana

Instana auto‑discovers Kubecost metrics and displays them under the Cost dashboard.
Metrics include allocation, idle cost, namespace cost, workload cost, and historical trends.
[ibm.com]
You should now see:

Total cluster cost trends
Namespace‑level cost breakdowns
Deployment/resource‑level insights
Idle/spare capacity cost
Release markers overlaying cost trends [community.ibm.com]

4. Correlate cost with performance and deployments

Compare cost widgets side‑by‑side with built‑in performance dashboards (latency, errors, throughput).
[community.ibm.com]
Use release markers to quickly identify which deployments correlate with sudden cost spikes. [community.ibm.com]
If performance regressed while cost increased, validate container resource requests/limits.

5. Recommend a cost optimization action

Identify inefficiency: over‑requested CPU, unused namespace resources, noisy‑neighbor workloads, etc.
Recommend one FinOps action: right‑size resource requests; scale down idle workloads; consolidate namespaces; or adjust HPA behavior based on cost.
Document expected savings using insights from Kubecost and Instana side‑by‑side views.
[ibm.com]

Validation checks (what “done” looks like)
To pass this pattern, you must demonstrate:

Instana successfully pulling Kubecost data (verified in Cost dashboards).
Cluster‑level → namespace‑level → workload‑level visibility. [ibm.com]
Clear walk-through of cost trend analysis with performance context.
(e.g., “Deployment X increased container memory requests → cost spike → correlated latency improvement or regression”). [community.ibm.com]
A concise optimization recommendation with measurable projected impact.

Outputs for assessment

2–4 minute video (or part of the main module video) showing:

Cost dashboard in Instana (cluster → namespace → workload).
Release marker correlation.
Identifying inefficiencies with Kubecost data.
Performance correlation from Instana metrics/traces.
Your recommended optimization and expected savings.
[ibm.com], [community.ibm.com]

Top troubleshooting cues

No cost data shown in Instana:

Verify Kubecost is deployed in the same cluster monitored by Instana.
Check Kubecost sensor config (url, auth, and cluster names).
If using Enterprise Kubecost: validate API key and Kubecost Product Key are active.
[ibm.com]

Only one cluster detected:

Free tier only supports single-cluster monitoring; upgrade or configure dynamic detection.
[ibm.com], [community.ibm.com]

Data mismatches:

Ensure cluster naming in Instana matches Kubecost’s configuration.
Verify time window alignment when comparing trends.

Appendix — Recommended text blocks
Tagging & labeling best practices
Consistent Kubernetes labels (app, team, environment, cost-center) improve cost allocation and namespace breakdowns.
[ibm.com]
Suggested KPIs

Cost per namespace
Cost per workload / per deployment
Cost per request or per transaction
Idle cost ratio
Allocation vs. request efficiency

References (public docs)

Integrating Kubecost with Instana for Kubernetes cost insights [community.ibm.com]
IBM Instana cost & performance insights powered by Kubecost [ibm.com]
Unlock Kubernetes cost insights with Instana + Kubecost [community.ibm.com]
Setting up Instana–Kubecost integration (static/dynamic cluster detection, API key use) [community.ibm.com], [ibm.com]
Amazon EKS cost optimization using Instana + Kubecost

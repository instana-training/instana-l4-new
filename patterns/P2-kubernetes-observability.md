# Pattern Card P2 - Kubernetes observability

- **Module:** M1 - Core Observability
- **Version:** March 2026

## Intent

Instrument a Kubernetes (K8s) cluster end-to-end and troubleshoot a workload issue by correlating infrastructure signals (nodes, namespaces, workloads, pods, events) with application signals (services, traces, logs, metrics). Use the Kubernetes platform view to locate the problem, follow topology to affected services, and validate user-visible impact with traces/logs and relevant golden signals (latency, traffic, error rate). The learner should finish able to explain *what broke, where, why, and who/what was impacted* using clear evidence captured in the tool.  

> **Note:** All names in this pattern are examples only. Replace with your environment's cluster, namespace, and service names.

## Prerequisites

- A Kubernetes cluster where you can deploy an observability agent using **Operator** or **Helm** (cluster-admin or equivalent required).
- Network egress from cluster nodes to the observability backend (HTTPS), and permission to pull agent images from a registry.
- Ability to deploy a simple test workload and to **simulate a failure** (for example: CrashLoopBackOff, OOMKill, Pending pods due to quota, or a 5xx spike).  
- Access to application traces and container logs through the observability platform (either native collection or via integrated log/trace sources).
- (Optional) A lightweight traffic generator to produce baseline and degraded load.

## Example scenario

1. Deploy the agent with Helm or an Operator and confirm that the cluster, nodes, namespaces, and workloads are discovered.  
2. Deploy a sample application (any stateless HTTP service is fine) and generate normal traffic.  
3. Introduce a failure condition (for example, reduce container memory limit to trigger OOMKill or introduce a dependency error to trigger 5xx).  
4. Use Platforms -> Kubernetes (or equivalent) to find the unhealthy pod/workload; pivot to the service map/topology; review events and resource requests/limits.  
5. Open related traces/logs to corroborate user-visible impact and isolate the root cause.  
6. Summarize findings: fault domain, contributing factors (for example, resource pressure), and downstream impact.

## Build recipe

> The following tasks are expressed as generic, environment-agnostic steps. Use either Operator or Helm; choose what matches your environment's standards.

### Task - Install and configure the Kubernetes agent

**Step 1 - Choose an installation method**  

- Decide between **Operator** (declarative lifecycle, CR-driven) or **Helm** (chart-driven).  
- Identify required values: backend endpoint/keys, cluster and zone identifiers, namespace for installation, proxy settings if any.

**Step 2 - Prepare the cluster**  

- Ensure your service account has cluster-level permissions to watch K8s resources (RBAC rules/ClusterRoleBindings).  
- Verify nodes have outbound connectivity to the backend and container registry.  
- Confirm supported container runtime (for example, containerd) and that admission controllers/policies (for example, Pod Security Standards, Gatekeeper, Kyverno) permit the agent DaemonSet/Operator pods to run.

**Step 3 - Deploy the agent**  

- Navigate to Agent installation page in the Instana console and choose the agent installation method.
- Using **Operator**: install the Operator, then apply the custom resource (CR) with your configuration.  
- Using **Helm**: template or install the chart with your values file; set cluster/zone tags and any namespace filters.  
- Validate that a **DaemonSet** (or equivalent) is running on all schedulable nodes and any required cluster collectors are healthy.

**Step 4 - Verify discovery and data quality**  
- In the platform's Kubernetes view, confirm the cluster appears with all nodes, namespaces, workloads, and pods.  
- Check host/Node KPIs (CPU, memory, disk, network) and container metrics at the expected scrape interval.  
- Spot-check one application service to ensure traces/logs are linked to pods/containers.

### Task - Validate application and platform correlation
**Step 1 - Establish the baseline**  
- Select one application; note golden signals: **Calls/Throughput**, **Latency**, **Error rate**.  
- Capture a short time window screenshot as "baseline".

**Step 2 - Introduce a controlled fault**  
- Pick one fault type (examples):  
  - Misconfigured resource **limits** -> pod **OOMKill** and restarts  
  - Liveness/readiness probe failure -> **CrashLoopBackOff**  
  - Network egress policy change -> downstream **timeouts**  
  - Quota exceeded -> pods remain **Pending**
- Annotate the exact time the fault is introduced.

**Step 3 - Investigate from the platform view**  
- Open Platforms -> Kubernetes and filter to the affected cluster/namespace.  
- Use Topology/Map to locate unhealthy nodes/workloads/pods; review Kubernetes **Events** to see scheduling/probe/oom events.  
- Inspect the workload's **requests/limits**, last restart reason, and recent changes.

**Step B4 - Pivot to application context**  
- From the affected workload/pod, open the linked **service** and **transactions/traces**.  
- Identify elevated latency or error rate on paths that traverse the failing component.  
- Open related **logs** (pod/container) and correlate timestamps with trace spans and K8s events.

**Step B5 - Summarize and tag the incident**  
- Record: fault type, root cause, impacted services, user-visible symptoms, and key evidence (metrics/events/traces/logs).  
- Add a note/annotation in the platform (if supported) with the conclusion for easy scoring and later review.

### Task C - Hardening, alerting, and hygiene (optional but recommended)
**Step C1 - Event and alert coverage**  
- Define smart alerts or equivalent for: pod restart storms, OOMKill counts, crash loops, high error rate, and saturation (CPU/memory) breaching SLOs.  
- Scope alerts to namespaces/labels rather than individual pods to remain resilient to churn.

**Step C2 - Metadata and labeling**  
- Ensure workloads carry consistent labels (team, application, tier, environment) to enable meaningful filtering and ownership routing.  
- Confirm these labels appear in traces and logs for seamless correlation.

**Step C3 - Cost/performance insights (optional)**  
- If integrated with a cost or resource optimization tool, capture a recommendation (for example, right-size CPU/memory) and show how it relates to observed saturation or idle capacity. Treat any product names you see in lab guides as examples only.

## Validation checks
- **Agent health:** All expected DaemonSet/Operator pods ready; cluster, nodes, and namespaces visible.  
- **Discovery:** Target workload present with correct requests/limits and labels.  
- **Correlation:** From a failing pod you can navigate to the impacted service and open related traces and logs within the same time window.  
- **Impact evidence:** A chart or table shows a change in at least one golden signal (latency, errors, or throughput) that aligns with the K8s Event timeline.  
- **Root cause narrative:** A 3 to 5 bullet explanation ties K8s condition -> service impact -> user symptom, with screenshots or links.

## Outputs for assessment
- **Short recording (3 to 5 minutes):** install method and key config -> failure injection -> investigation path (K8s view -> service map -> traces/logs) -> conclusion.  
- **Screenshot pack (5 to 8 images):** cluster discovery, workload details, Events, service KPIs, trace detail, log snippet.  
- **One-page summary:** fault type, suspected root cause, affected services, and remediation next steps.  
- (Optional) **Alert definition(s):** export or screenshot of one alert you would keep enabled in production for this scenario.

## Top troubleshooting cues
- **Agent not scheduling:** Check namespace/pod security policies, tolerations/taints, node selectors, and admission controls; verify required capabilities and host mounts are permitted.  
- **RBAC/visibility gaps:** Ensure ClusterRole/ClusterRoleBinding allow watch/list on pods, deployments, nodes, events, and related APIs. Missing permissions often manifest as partial topology.  
- **Egress/connectivity issues:** Validate outbound HTTPS to the backend and container registry access; confirm proxy configuration if used.  
- **Namespace filters:** Review include/exclude lists and label selectors to avoid unintentionally hiding namespaces or workloads.  
- **Time skew:** Significant clock drift between nodes/backends breaks correlation across metrics, events, traces, and logs. Enable NTP/Chrony.  
- **High churn or sampling confusion:** Ensure the platform is configured for the desired tracing mode and that high-cardinality labels are bounded to avoid UI slowdowns.  
- **Container restarts/OOM:** Inspect recent image/config changes, requests/limits, and memory leak patterns; correlate OOMKill events with pod restarts and service error spikes.  
- **Log ingestion gaps:** Confirm log collection is enabled for the namespace/workload and not blocked by size/retention policies.

## Related hands-on labs
- L1 Agent installation on Kubernetes (Operator and Helm)
- L2 Application tracing and dependency mapping
- L3 Alerting and automation with smart alerts and runbooks
- L4 Cost/performance insights for Kubernetes (optional)

## Related pattern cards
- P12 Cost Insights and FinOps  
- P8 Log management and analytics  
- P5 SLOs and golden signals for microservices

## References (public docs)
- Installing the agent on Kubernetes - IBM Instana documentation (public)  
- Monitoring Kubernetes - IBM Instana documentation (public)
## References (public docs)

- [Installing the agent on Kubernetes](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=agents-installing-kubernetes)
- [Monitoring Kubernetes](https://www.ibm.com/docs/en/instana-observability/1.0.315?topic=instana-monitoring-kubernetes)


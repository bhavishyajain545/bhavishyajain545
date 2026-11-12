# Hi, I'm Bhavishya Jain

DevOps / SRE engineer focused on Kubernetes, GitOps and observability. I contribute to CNCF projects (Kyverno, KEDA, Argo CD, OpenTelemetry) and I am preparing for LFX Mentorship and Google Summer of Code 2027.

## What I work with

- **Platforms:** Kubernetes (GKE, AKS, EKS, k3s), Docker
- **IaC & GitOps:** Terraform, ArgoCD, Argo Rollouts, Helm
- **Observability:** Prometheus, Grafana, Loki, Alloy, SLO / burn-rate alerting
- **CI/CD & Cloud:** GitHub Actions, GCP, AWS, Azure
- **Languages:** Go, Python, Bash

## Open source

How I find work to do: I diff what the code accepts (struct tags, CLI flags, ConfigMap keys) against what the docs describe, and I pick up maintainer-filed bugs that nobody has claimed. Every change below comes with a test that fails before the fix and passes after it.

### Code

| Project | Change | Status |
| --- | --- | --- |
| [kyverno/kyverno#18571](https://github.com/kyverno/kyverno/pull/18571) | CLI `--set` dropped any value containing `=` (URLs, base64); split on the first `=` only, regression tests, package `AGENTS.md` | open |
| [kyverno/reports-server#362](https://github.com/kyverno/reports-server/pull/362) | APIService reconciler issued three no-op updates every 10s because `spec.service.port` was left for the apiserver to default; set it explicitly, tests assert the `DeepEqual` converges | open |
| [kyverno/reports-server#363](https://github.com/kyverno/reports-server/pull/363) | Streaming-list watches (`sendInitialEvents`) never sent the `k8s.io/initial-events-end` bookmark, so client-go reflectors hung; implemented across all six Watch handlers with a shared helper | open |
| [kyverno/reports-server#365](https://github.com/kyverno/reports-server/pull/365) | `GOMEMLIMIT` was hardcoded to 100% of the memory limit (OOM kills, not overridable); replaced with `automemlimit` at 90%, flags and chart values | open |

### Bugs I found and reported

- [kedacore/keda#8358](https://github.com/kedacore/keda/issues/8358): Datadog scaler ignores `activationQueryValue` when `useClusterAgentProxy` is on (reads `activationTargetValue` instead)
- [kedacore/keda#8359](https://github.com/kedacore/keda/issues/8359): Solace Direct Messaging scaler accepts four `activation*` parameters that nothing reads

### Documentation

- Kyverno: [missing container flags + typo](https://github.com/kyverno/website/pull/2274), [VAP reports opt-in label and paramKind RBAC](https://github.com/kyverno/website/pull/2273)
- KEDA: [undocumented scaler parameters](https://github.com/kedacore/keda-docs/pull/1938), [Solace DM targets and MongoDB TLS](https://github.com/kedacore/keda-docs/pull/1939)
- Argo CD: [15 missing `argocd-cmd-params-cm` keys](https://github.com/argoproj/argo-cd/pull/30933), with corrections from code review on CSP, X-Frame-Options and gRPC limits
- OpenTelemetry Collector: [`block_on_overflow`](https://github.com/open-telemetry/opentelemetry-collector-contrib/pull/53014) and three more component options found with the same audit

## Highlighted projects

- [docdrift](https://github.com/bhavishyajain545/docdrift) - Finds configuration options that exist in Go code (struct tags, flags, ConfigMap keys) but are missing from the docs; the tool behind the contributions above
- [gcp-gke-platform](https://github.com/bhavishyajain545/gcp-gke-platform) - GKE Autopilot platform: Go microservice, Terraform, GitHub Actions (WIF) CI, ArgoCD GitOps, Managed Prometheus SLOs
- [terraform-cloud-blueprints](https://github.com/bhavishyajain545/terraform-cloud-blueprints) - Production-minded Terraform modules for AKS and EKS with mock-provider tests, tflint and checkov in CI
- [observability-slo-stack](https://github.com/bhavishyajain545/observability-slo-stack) - SLOs as code on k3s: kube-prometheus-stack, Loki, Alloy and multi-window multi-burn-rate alerts
- [homelab-gitops](https://github.com/bhavishyajain545/homelab-gitops) - Single-node k3s homelab managed with ArgoCD app-of-apps and Argo Rollouts canary delivery
- [gcp-gemini-rag-agent](https://github.com/bhavishyajain545/gcp-gemini-rag-agent) - DevOps on-call agent: Google ADK + Gemini on Vertex AI, runbook RAG, Cloud Run, Terraform

## Reach me

Open to DevOps / SRE / Platform Engineering opportunities. Feel free to connect here on GitHub.

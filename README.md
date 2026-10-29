# PayFlow Platform

A production-style DevOps platform for **PayFlow**, a small fintech (digital payments) application, deployed end to end from a single command on a local Kubernetes cluster or on AWS.

> **Status:** Work in progress, built in public, phase by phase. See the [build journal](docs/journal/).

## Goal

Show how a real delivery pipeline works, from a code commit to a running, monitored, secured service:

- **One-command deploy:** `./platform.sh up local` or `./platform.sh up aws` — Terraform creates the cluster, ArgoCD installs everything else from Git.
- **GitOps:** Git is the only way to change the cluster. CI builds images and updates tags; ArgoCD deploys them.
- **Separation of duties:** GitHub Actions builds, Jenkins tests and gates promotion to prod, ArgoCD deploys.
- **Production practices:** observability, alerting, secrets management, network policies and policy-as-code.

Anyone — a recruiter, an engineer or another learner — should be able to clone this repo and run the full platform on their own machine.

## Tech stack

| Area | Tools |
|---|---|
| Containers | Docker |
| Orchestration | Kubernetes (kind locally, Amazon EKS on AWS) |
| Packaging | Helm |
| Infrastructure as Code | Terraform |
| CI | GitHub Actions |
| Release gate | Jenkins |
| CD / GitOps | ArgoCD |
| Observability | Prometheus, Grafana, Alertmanager |
| Security | Trivy, Sealed Secrets, Kyverno, NetworkPolicies |
| Scripting | Bash, Python |
| Cloud | AWS |

## Repositories

| Repo | Purpose |
|---|---|
| [payflow-app](https://github.com/owais-io/payflow-app) | Application code: accounts-api, payments-api, notification-worker, frontend |
| **payflow-platform** (this repo) | Infrastructure, deployment, CI/CD, monitoring, security and docs |

## Quick start

_Coming in Phase 9._

## License

MIT

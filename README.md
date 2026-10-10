# PulseOps Kubernetes GitOps Manifests

This repository is the **single source of truth** for Kubernetes infrastructure, declarative microservice deployments, and ArgoCD synchronization for the PulseOps platform.

## Repository Layout
```text
.
├── base/                   # Shared templates for all services
│   ├── backend/            # Express API (Deployment, Service)
│   ├── frontend/           # React Dashboard (Deployment, Service)
│   ├── postgres/           # Database (StatefulSet, Headless Service)
│   └── kustomization.yaml
└── environments/
    ├── dev/                # Dev environment (nip.io / IP Ingress, 1 replica)
    └── prod/               # Prod environment (High availability, Custom domain TLS)
```

## Quick Commands
```bash
# Preview generated dev manifests locally:
kubectl kustomize environments/dev

# Apply dev environment:
kubectl apply -k environments/dev
```

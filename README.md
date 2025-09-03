# GitOps Deployment with EKS and ArgoCD

## Overview
This repo demonstrates GitOps workflow using:
- AWS EKS
- ArgoCD
- GitHub

## Flow
1. ArgoCD watches this repo.
2. On every commit, ArgoCD syncs manifests into EKS.
3. Application gets deployed/updated automatically.

## Repo Structure
- `k8s-manifests/`: Kubernetes YAML files (namespace, deployment, service, ingress).
- `argocd-apps/`: ArgoCD Application definition.
- `helm-chart/`: (Optional) Helm-based deployment.

## How to Use
1. Apply `argocd-apps/sample-app.yaml` inside ArgoCD namespace:
   ```bash
   kubectl apply -f argocd-apps/sample-app.yaml -n argocd


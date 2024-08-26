#### Commands

```bash
# Install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# Login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```
</br>

# Kubernetes Deployment with Argo CD

This repository contains configurations for deploying applications using Argo CD. It includes Kubernetes manifest files, custom Helm charts, and public Helm charts.

## Directory Overview

- **dev/**: Contains standard Kubernetes manifest files for deploying applications directly with Kubernetes using argo-cd.

- **helm-guestbook/**: Contains a custom Helm chart for deploying a guestbook application with custom-values using argo-cd.

- **nginx/**: Contains configuration for deploying Nginx using a public Helm chart with custom values using argo-cd.
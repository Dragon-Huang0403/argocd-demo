# Infra

## Set up

1. Create Project

```sh
argocd proj create infra \
  -d https://kubernetes.default.svc,argocd \
  --src "*"

argocd proj allow-cluster-resource \
  infra "*" "*"
```

2. Self-managed argo-cd

```sh
argocd app create argo-cd \
  --project infra \
  --repo https://github.com/argoproj/argo-cd \
  --revision v2.10.7 \
  --path manifests/cluster-install \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace argocd
```

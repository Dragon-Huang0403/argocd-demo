# Applications

## Set up

1. Create Project

```sh
argocd proj create applications \
  -d https://kubernetes.default.svc,argocd \
  -s https://github.com/dragon-Huang0403/argocd-demo
```

2. Create Application

```sh
argocd app create applications \
  --project applications \
  --repo https://github.com/dragon-Huang0403/argocd-demo \
  --path applications \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace argocd \
  --sync-policy automated \
  --set-finalizer
```

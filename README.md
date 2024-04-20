# homelab-cluster
related to k8 cluster configuration


### helpful commands:

remove finalizer in argo to un-stick deletes:
```shell
kubectl patch applications.argoproj.io/<application-name> -n argocd --type json --patch='[ { "op": "remove", "path": "/metadata/finalizers" } ]'
```
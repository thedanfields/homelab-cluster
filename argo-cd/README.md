### tell Argo to run insecurely:

```shell
kubectl -n argocd patch deployment argocd-server --type json -p='[ { "op": "replace", "path":"/spec/template/spec/containers/0/command","value": ["argocd-server","--insecure"] }]'
```

### non-gateway access:

```shell
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "ClusterIP"}}'
```

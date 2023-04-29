https://picluster.ricsanfre.com/docs/loki/

kubectl api-resources --verbs=list --namespaced -o name \
 | xargs -n 1 kubectl get --show-kind --ignore-not-found -l <label>=<value> -n loki

kubectl patch applications.argoproj.io/loki -n loki --type json --patch='[ { "op": "remove", "path": "/metadata/finalizers" } ]'

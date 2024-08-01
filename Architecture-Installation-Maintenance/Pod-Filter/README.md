# update the pod-filter.sh

```
#!/bin/bash
kubectl get pod nginx-pod -o jsonpath='{.metadata.labels.application}'

```

## Run the below command

Edit the network policy
```
kubectl edit networkpolicy allow-green-and-blue
```

Delete the blue-pod from ingress
```
# Please edit the object below. Lines beginning with a '#' will be ignored,
# and an empty file will abort the edit. If an error occurs while saving this file will be
# reopened with the relevant failures.
#
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"networking.k8s.io/v1","kind":"NetworkPolicy","metadata":{"annotations":{},"name":"allow-green-and-blue","namespace":"default"},"spec":{"ingress":[{"from":[{"podSelect
  creationTimestamp: "2024-08-11T05:16:48Z"
  generation: 1
  name: allow-green-and-blue
  namespace: default
  resourceVersion: "3038"
  uid: ff0d430a-7e16-46e2-b965-3289acbe1ee7
spec:
  ingress:
  - from:
    - podSelector:
        matchLabels:
          run: green-pod
  podSelector:
    matchLabels:
      run: red-pod
  policyTypes:
  - Ingress
```
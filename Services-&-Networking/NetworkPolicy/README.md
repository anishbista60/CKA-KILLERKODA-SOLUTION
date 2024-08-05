## create the Netpol manifest 

```
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: my-app-network-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      app: my-app
  policyTypes:
  - Ingress
  - Egress
  ingress:
  - from:
    - podSelector: {}
  - from:
    - podSelector:
        matchLabels:
          app: trusted
  egress:
  - to:
    - podSelector: {}
```
## Create the namspace 

```
k create ns dns-ns
```
## create the deployment 

```
apiVersion: apps/v1
kind: Deployment
metadata:
  creationTimestamp: null
  labels:
    app: dns-deploy-cka
  name: dns-deploy-cka
  namespace: dns-ns
spec:
  replicas: 2
  selector:
    matchLabels:
      app: dns-deploy-cka
  strategy: {}
  template:
    metadata:
      creationTimestamp: null
      labels:
        app: dns-deploy-cka
    spec:
      containers:
      - image: registry.k8s.io/e2e-test-images/jessie-dnsutils:1.3
        name: dns-container
        command: ["sleep"," 3600"]
        resources: {}
status: {}
```

## Exec inside one pod and run the below command 
```
kubectl exec -n dns-ns $POD_NAME -- nslookup kubernetes.default > dns-output.txt
```
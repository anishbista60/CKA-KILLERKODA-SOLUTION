## Run the below command

create namespace
```
c

```

create rs.yaml
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: dns-rs-cka
  namespace: dns-ns
spec:
  replicas: 2
  selector:
    matchLabels:
      app: dns-app
  template:
    metadata:
      labels:
        app: dns-app
    spec:
      containers:
        - name: dns-container
          image: registry.k8s.io/e2e-test-images/jessie-dnsutils:1.3
          command: ["sleep", "3600"]

```

apply the manifest
```
kubectl apply -f rs.yaml

```

exec inside one pod and run the command + save it to the file
```
kubectl exec -n dns-ns $POD_NAME -- nslookup kubernetes.default > dns-output.txt

```
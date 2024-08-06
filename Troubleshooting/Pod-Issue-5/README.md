## Run the below command

Apply redis-pod.yaml and check the error
```
kubectl apply -f redis-pod.yaml

```

![alt text](image.png)

Update the redis-pod.yaml
```
apiVersion: v1
kind: Pod
metadata:
  name: redis-pod
spec:
  containers:
    - name: redis-container
      image: redis:latest
      resources:
        requests:
          memory: "100Mi"
          cpu: "10m"
        limits:
          memory: "100Mi"
          cpu: "10m"
```

Apply the manifest
```
kubectl apply -f redis-pod.yaml

```
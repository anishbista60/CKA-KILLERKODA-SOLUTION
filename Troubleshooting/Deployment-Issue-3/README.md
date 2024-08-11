## Run the below command


```
kubectl describe deploy postgres-deployment
k describe pod postgres-deployment-669f98658f-j9fqx
```

configmap name is not matching.

Change the name postgres-db-config to postgres-config

Similarly, for secret name.

```
kubectl edit deploy postgres-deployment
```

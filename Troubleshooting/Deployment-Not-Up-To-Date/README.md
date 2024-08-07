## Run the below command

Check the deployment
```
kubectl describe deploy stream-deployment
```

0/0 replicas are created.

Edit the deployment

```
kubectl edit deploy stream-deployment
```

Make replicas to 1.
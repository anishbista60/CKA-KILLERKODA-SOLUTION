## Run the below command

Expose the pod
```
kubectl expose pod/nginx-pod --name nginx-service

```

Port forward
```
k port-forward service/nginx-service 8080:80

```
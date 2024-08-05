## Run the below command

Check the pod
```
kubectl describe pod frontend

```
This is the issue whcih says that nodeAffinity did not match
![alt text](image.png)

Check the node labels
```
kubectl get nodes --show-labels

```

```
kubectl get pods frontend -oyaml > pod.yaml
```

NodeName=frontendnodes is the real one but in pod it is only mentioned frontend
So change the nodeAffinity values to frontendnodes.

![alt text](image-1.png)

Delete the running pod
```
kubectl delete pod frontend

```

Apply pod.yaml
```
kubectl apply -f pod.yaml

```

Now, wait for pod to get to the running state.


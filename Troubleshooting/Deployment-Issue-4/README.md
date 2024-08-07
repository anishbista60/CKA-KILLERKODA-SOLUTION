## Run the below command

Describe the pod
```
kubectl describe pod <pod-name>

```

you will see volume error

```
kubectl edit deploy database-deployment

```
 
Change the pvc name in volumes to actual pvc name `postgres-pvc`


Describe pv and pvc
```
kubectl describe pv postgres-pv
kubectl describe pvc postgres-pvc
```

The accessMode of pv and pvc is mismatched. Make pv as `ReadWriteMany`


The pv capacity is lesser than pvc capacity. Make pv capacity equal to pvc capacity.


Wait for pod to get to running state.



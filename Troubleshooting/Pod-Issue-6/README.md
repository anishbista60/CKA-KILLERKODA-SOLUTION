## Run the below command

Describe the pod
```
kubectl describe pod my-pod-cka

```

![alt text](image.png)

Check the PersistentVolume and PersistentVolumeClaim
![alt text](image-1.png)

PV is is Available state.

Edit the PV
```
kubectl edit pv my-pv-cka

```

Access mode of pv and pvc are different
Edit the pv to be same as of pvc
![alt text](image-2.png)

Wait for the pod to get into running state.
## Run the below command

At first, the kubectl command will show error.
Wait for some seconds and it will start showing up.

Get all 
```
kubectl get all -A
```

You will see that 0/1 in READY for apiserver-controlplane

```
kubectl describe pod kube-apiserver-controlplane -n kube-system
```

Startup probe is failed.

Check the manifest.
```
vi /etc/kubernetes/manifests/kube-apiserver.yaml 
```

Port for probes is defined as 6433 but should be 6443.
Same as above for LivenessProbe and Readliness Probe. Please change it to 6443. 

Change it.

Wait for startup.

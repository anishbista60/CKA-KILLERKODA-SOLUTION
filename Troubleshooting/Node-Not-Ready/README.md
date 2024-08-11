## Run the below command

check the nodes
```
kubectl get nodes
```
After some time , control plane will show NotReady state.

Since the kubelet is not running in controlplane.Start it.

```
service kubelet start
``

Check the status
```
service kubelet status
```

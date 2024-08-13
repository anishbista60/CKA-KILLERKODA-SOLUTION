## Run the below command

```
kubectl get pvc
kubectl get pv
```

Describe pvc to see the error
```
kubectl describe pvc my-pvc
```

You will see error: No such storage class `standard`

Edit the pv

```
kubectl edit pv my-pv
```

set storageClassName to `slow`

For pvc
```
kubectl get pvc my-pvc -oyaml > a.yaml
```

```
kubectl delete pvc my-pvc --grace-period 0
```

```
vi a.yaml
```

Set the storageClassName to `slow` and apply.

Describe the pvc.

Error: 

    Cannot bind to requested volume "my-pv": requested PV is too small
    Cannot bind to requested volume "my-pv": incompatible accessMode

```
kubectl edit pv my-pv
```

Make changes:

    Change pv storage to same as pvc i.e. 150Mi
    change the acessMode to ReadWriteMany
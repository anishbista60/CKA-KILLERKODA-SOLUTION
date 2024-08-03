## Run the below command

Create sc.yaml
```
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: green-stc
  annotations:
    storageclass.kubernetes.io/is-default-class: "false"
provisioner: kubernetes.io/no-provisioner
reclaimPolicy: Retain # default value is Delete
allowVolumeExpansion: true
volumeBindingMode: WaitForFirstConsumer
```

Apply the yaml file
```
kubectl apply -f sc.yaml

```
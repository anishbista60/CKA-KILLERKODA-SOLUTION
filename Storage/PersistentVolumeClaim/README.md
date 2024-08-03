## Run the below command

Create pvc.yaml
```
vi pvc.yaml
```

Copy paste below code
```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: red-pvc-cka
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 30Mi
  storageClassName: manual
  volumeName: red-pv-cka
```

Apply the manifest
```
kubectl apply -f pvc.yaml

```
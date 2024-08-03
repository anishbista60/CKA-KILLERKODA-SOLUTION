## Run the below command

Create pv.yaml
```
vi pv.yaml

```
```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: gold-pv-cka
  labels:
    tier: white
spec:
  capacity:
    storage: 50Mi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteMany
  persistentVolumeReclaimPolicy: Retain
  storageClassName: gold-stc-cka
  hostPath:
    path: /opt/gold-stc-cka
  nodeAffinity:
    required:
      nodeSelectorTerms:
      - matchExpressions:
        - key: kubernetes.io/hostname
          operator: In
          values:
          - node01
```

Create pvc.yaml
```
vi pvc.yaml

```
```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: gold-pvc-cka
spec:
  accessModes:
    - ReadWriteMany
  volumeMode: Filesystem
  resources:
    requests:
      storage: 30Mi
  storageClassName: gold-stc-cka
  selector:
    matchLabels:
        tier: white
```

Apply these manifests
```
kubectl apply -f pv.yaml
kubectl apply -f pvc.yaml

```
## Run the below command

Create pv.yaml
```
vi pv.yaml

```
```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: my-pv-cka
spec:
  capacity:
    storage: 100Mi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Recycle
  storageClassName: standard
  hostPath:
    path: /mnt/data
```

Create pvc.yaml
```
vi pvc.yaml

```
```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc-cka
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 100Mi
  storageClassName: standard
  volumeName: my-pv-cka
```

Create pod.yaml
```
vi pod.yaml

```
```
apiVersion: v1
kind: Pod
metadata:
  name: my-pod-cka
spec:
  containers:
    - name: nginx
      image: nginx
      volumeMounts:
      - mountPath: "/var/www/html"
        name: mypd
  volumes:
    - name: mypd
      persistentVolumeClaim:
        claimName: my-pvc-cka 
```

Apply these manifests
```
kubectl apply -f pv.yaml
kubectl apply -f pvc.yaml
kubectl apply -f pod.yaml

```
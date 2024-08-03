## Run the below command

Create pvc.yaml
```
vi pvc.yaml

```
```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: nginx-pvc-cka
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 80Mi
  storageClassName: nginx-stc-cka
  volumeName: nginx-pv-cka
```

Edit nginx-pod-cka.yaml
```
vi nginx-pod-cka.yaml

```
```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod-cka
spec:
  containers:
    - name: my-container
      image: nginx:latest
      volumeMounts:
        - name: mypd
          mountPath: "/var/www/html"
  tolerations:
  - key: "node-role.kubernetes.io/control-plane"
    operator: "Exists"
    effect: "NoSchedule"
  volumes:
  - name: mypd
    persistentVolumeClaim:
      claimName: nginx-pvc-cka
```

Apply the manifests
```
kubectl apply -f pvc.yaml
kubectl apply -f nginx-pod-cka.yaml

```
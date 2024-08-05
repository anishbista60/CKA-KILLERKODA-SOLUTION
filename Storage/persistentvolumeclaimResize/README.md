## Edit the PVC manifest

```
k edit pvc yellow-pvc-cka
```
## Change the storage to `60Mi` from `40Mi`
```
spec:
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: 60Mi
```
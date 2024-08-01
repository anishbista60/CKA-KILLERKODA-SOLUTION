# RUN the below command


```
apiVersion: v1
kind: Pod
metadata:
  name: alpine-pod-pod
spec:
  containers:
  - name: alpine-container
    image: alpine:latest
    command: ["/bin/sh", "-c"]
    args: ["tail -f /config/log.txt"]
    volumeMounts:
    - name: config-volume
      mountPath: /config
  volumes:
  - name: config-volume
    configMap:
      name: log-configmap
  restartPolicy: Never


```

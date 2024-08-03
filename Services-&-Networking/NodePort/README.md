## Create the service manifest

```
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: null
  labels:
    app: nginx-app-cka
  name: app-service-cka
  namespace: nginx-app-space
spec:
  ports:
  - port: 80
    protocol: TCP
    targetPort: 80
    nodePort: 31000
  selector:
    app: nginx-app-cka
  type: NodePort
status:
  loadBalancer: {}
```
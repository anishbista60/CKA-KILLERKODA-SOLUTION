## Run the below command

Create Deployment
```
k create deploy my-web-app-deployment --image=wordpress --replicas=2

```

Expose the deployment
```
k expose deploy/my-web-app-deployment --name=my-web-app-service --type=NodePort --port=80 --dry-run=client -oyaml > svc.yaml

```

Edit the svc.yaml to add nodePort
```
vi svc.yaml
```
```
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: null
  labels:
    app: my-web-app-deployment
  name: my-web-app-service
spec:
  ports:
  - port: 80
    protocol: TCP
    targetPort: 80
    nodePort: 30770
  selector:
    app: my-web-app-deployment
  type: NodePort
status:
  loadBalancer: {}
```

Apply the svc.yaml file
```
kubectl apply -f svc.yaml

```
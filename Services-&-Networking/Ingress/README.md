## Run the below command 
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-ingress-resource
  annotations:
    nginx.ingress.kubernetes.io/ssl-redirect: "false"
spec:
  ingressClassName: nginx-example
  rules:
  - http:
      paths:
      - path: /shop 
        pathType: Prefix
        backend:
          service:
            name: nginx-service 
            port:
              number: 80
```
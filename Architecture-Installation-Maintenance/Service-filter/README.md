## Your svc-filter.sh should look like
```
#!/bin/bash
  
kubectl get service redis-service -o jsonpath='{.spec.ports[0].targetPort}'

```
Check if it is working correctly
```
chmod 777 svc-filter.sh
./svc-filter.sh

```
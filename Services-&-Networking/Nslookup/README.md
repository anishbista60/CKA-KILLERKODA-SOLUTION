## Run the below command

Create pod
```
kubectl run nginx-pod-cka --image=nginx

```

Expose the pod
```
kubectl expose pod/nginx-pod-cka --name=nginx-service-cka --port=80

```

Run busybox pod
```
kubectl run busybox --image=busybox --restart=Never --command -- sleep 3600

```

Save nslookup result to nginx-service.txt
```
kubectl exec -it busybox -- nslookup nginx-service-cka > nginx-service.txt

```

This will be the result which is not required.
```
controlplane $ cat nginx-service.txt 
Server:         10.96.0.10
Address:        10.96.0.10:53

** server can't find nginx-service-cka.cluster.local: NXDOMAIN

Name:   nginx-service-cka.default.svc.cluster.local
Address: 10.102.139.91

** server can't find nginx-service-cka.svc.cluster.local: NXDOMAIN

** server can't find nginx-service-cka.cluster.local: NXDOMAIN


** server can't find nginx-service-cka.svc.cluster.local: NXDOMAIN

```

Another file nginx-service-test.txt will be generated
```
rm nginx-service.txt
mv nginx-service-test.txt nginx-service.txt

```
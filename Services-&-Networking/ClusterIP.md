## Run the below command

Part-I
```
k expose deploy/nginx-deployment --name nginx-service --port=8080 --target-port=80

```

Part-II
```
{ echo "IP_ADDRESS"; kubectl get pods -o jsonpath='{.items[*].status.podIP}' | tr ' ' '\n' | sort; } > pod_ips.txt

```
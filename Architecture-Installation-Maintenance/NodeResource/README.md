# Run the below command 

```
kubectl top nodes --no-headers | head -n 1 | awk -v ctx="$(kubectl config current-context)" '{print ctx "," $1}' > high_memory_node.txt

```

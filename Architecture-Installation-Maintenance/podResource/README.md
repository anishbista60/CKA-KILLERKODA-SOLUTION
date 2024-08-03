# Run the below command

```
a=$(k top pod -A --no-headers | sort -k3 -h -r | head -n1 | awk '{print $2}')

```

```
b=$(k top pod -A --no-headers | sort -k3 -h -r | head -n1 | awk 'print $1')
```


```
echo "$a,$b" > high_cpu_pod.txt

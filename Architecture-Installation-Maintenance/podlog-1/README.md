# first store the manifest of the product pod in `pod.yaml`

```
k get pod product -o yaml > pod.yaml

```

### Update the pod manifest in command section 

```
spec:
  containers:
  - command:
    - sh
    - -c
    - echo 'Sony Tv Is Good' && sleep 3600
```    

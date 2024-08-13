## There is issue in the manifest located at `/etc/kubernetes/kubelet.conf`. so , please change it to below 

```
server: https://172.30.1.2:6443
```
## Issue with manifest located at  `/vat/lib/kubelet/config.yaml`. So, please change it to below 

```
    clientCAFile: /etc/kubernetes/pki/ca.cert
```
 

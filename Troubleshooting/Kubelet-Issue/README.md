## Run the below code

Check logs
```
journalctl -xeu kubelet

```

![alt text](image.png)


Unable to load the certificate file

```
vi /var/lib/kubelet/config.yaml

```

Change to ca.crt
![alt text](image-1.png)


```
systemctl restart kubelet
systemctl status kubelet
```

Again check the logs
```
journalctl -xeu kubelet

```

Port Issue


![alt text](image-2.png)


```
vi /etc/kubernetes/kubelet.conf

```

Change the server to port 6443.

```
systemctl restart kubelet
systemctl status kubelet
```
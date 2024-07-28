## Run the below command

FOR CLUSTER BACKUP
```
ETCDCTL_API=3 etcdctl --endpoints 127.0.0.1:2379 \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  snapshot save /opt/cluster_backup.db

```

FOR CLUSTER RESTORE
```
ETCDCTL_API=3 etcdctl --data-dir /root/default.etcd \
  --endpoints 127.0.0.1:2379 \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  snapshot restore /opt/cluster_backup.db > restore.txt 2>&1

```

RESTORE IN CONTROLPLANE
```
vi /etc/kubernetes/manifests/etcd.yaml

```

Change ` --data-dir=/root/default.etcd `

In volumeMounts change `/var/lib/etcd ` to ` /root/default.etcd `

In volumes inside hostPath change ` /var/lib/etcd ` to ` /root/default.etcd `

Wait for etcd to start.

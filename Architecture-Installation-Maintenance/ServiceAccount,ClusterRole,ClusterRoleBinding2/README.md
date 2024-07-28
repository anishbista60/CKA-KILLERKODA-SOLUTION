## Run the below command

```
kubectl edit clusterrole group1-role-cka

```

ADD list,create IN verbs AND SAVE
```
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  creationTimestamp: "2024-07-30T08:43:41Z"
  name: group1-role-cka
  resourceVersion: "2817"
  uid: 558716cd-d846-42dd-8c00-4d360e1e38dc
rules:
- apiGroups:
  - apps
  resources:
  - deployments
  verbs:
  - get
  - list
  - create

```
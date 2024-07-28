## Run the below command

Edit THE SECRET FILE TO VIEW ENCODED CODE
```
kubectl edit secret database-data -n database-ns

```

COPY DB_PASSWORD AND REPLACE IT WITH <ADD_DB_PASSWORD>
```
echo "<ADD_DB_PASSWORD>" | base64 -d > decoded.txt

```
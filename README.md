```sh
kind create cluster --config kind-config.yaml
```

```sh
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.10.1/cert-manager.yaml
```

```sh
k run -it --rm percona-client --image=percona/percona-server-mongodb:5.0 -- mongo "mongodb+srv://clusterAdmin:clusterAdmin123456@mongodb-test-db-psmdb-rs0.mongodb-test.svc.cluster.local/admin?replicaSet=rs0&ssl=false"
```

```sh
k run -it --rm percona-client --image=percona/percona-server-mongodb:5.0 -- mongo "mongodb://clusterAdmin:clusterAdmin123456@mongodb-test-db-psmdb-mongos.mongodb-test.svc.cluster.local/admin?ssl=false"
```

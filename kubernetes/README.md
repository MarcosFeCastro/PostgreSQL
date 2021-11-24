# Kubernetes

## kind cluster
```
$ kind create cluster --name postgres
```

## Namespace
```
$ kubectl create ns postgres
```

# Postgres

## Storage Class - [Documentaton](https://kubernetes.io/docs/concepts/storage/storage-classes/)
```
$ kubectl apply -n postgres -f storage/postgres-local-storage.yaml
```
or
```
$ kubectl apply -n postgres -f storage/postgres-aws-storage.yaml
```
## Persistent Volumes - [Documentaton](https://kubernetes.io/pt-br/docs/concepts/storage/persistent-volumes/)
```
$ kubectl apply -n postgres -f postgres-volume.yaml
```
## Config
```
$ kubectl apply -n postgres -f postgres-configmap.yaml
```
## Secrets
```
$ kubectl apply -n postgres -f postgres-secret.yaml
``` 
## Deploy
```
$ kubectl apply -n postgres -f postgres-statefulset.yaml
```

# PgAdmin

## Persistent Volumes
```
$ kubectl apply -n postgres -f pgadmin/pgadmin-volume.yaml
```
## Config
```
$ kubectl apply -n postgres -f pgadmin/pgadmin-configmap.yaml
```
## Secrets
```
$ kubectl apply -n postgres -f pgadmin/pgadmin-secret.yaml
```
## Deploy
```
$ kubectl apply -n postgres -f pgadmin/pgadmin-deployment.yaml
```

```
$ kubectl get pods -n postgres
```

```
$ kubectl -n postgres port-forward <pod-name> 15432:80
```
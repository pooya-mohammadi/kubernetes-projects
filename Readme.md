
# Mongo Application
## Applying a secret file
1. The secrete file should be applied before other files to make the matching possible.

```commandline
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo-deployment.yaml
```
What pods till it gets created:
```commandline
kubectl get pod --watch 
# Or check the description
kubectl describe pod mongodb-deployment-7bb6c6c4c7-42p6m
```

## Check all mongo application
```commandline
kubectl get all | grep mongo
```

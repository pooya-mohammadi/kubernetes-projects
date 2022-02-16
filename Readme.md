
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
kubectl describe pod mongodb-deployment-7bb6c6c4c7-42p6m # the name will defer each time!
```

## Check all mongo application
```commandline
kubectl get all | grep mongo
```

## To apply mongodb-express:
```commandline
# first, apply mongo-config since mongo-express is bound to it
kubectl apply -f mongo-configmap.yaml
kubectl apply -f mongo-express-deployment.yaml
```
### Check connection
Check the logs to make sure that the express server is started and connected to the database:
```commandline
kubectl logs mongo-express-645b86fd6d-trjh6
```

### minicube ip address:
Execute the following to have a public address
```
minikube service mongo-express-service
```

To create a database following connections are done!:

<img src="https://raw.githubusercontent.com/pooya-mohammadi/kubernetes-projects/master/images/mongo-connections.png" alt="mongo-connections">
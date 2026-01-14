# Assignment-5 (DevSecOps 2025)
Following demo in from [Tutorial video by Techworlwith Nana](https://www.youtube.com/watch?v=s_o8dwzRlu4) with modification to deploy on **Azure Kubernetes Service (AKS)**

## Prerequisite
1. kubectl connected to an active kubernetes cluster
2. kubernetes node use **amd64** architecture cpu (required by webapp image)

## How to run
1. Create secret for mongo called `mong-user` (base64 encoded user for MongoDB) and mongo-password (base64 encoded password for MongoDB)
2. Replace mongoDB user (replace  `base64user`) and password(replace `base64password`) in `mongo-secret.yaml` to be base64 encoded user and password to your mongoDB
3. run following commands in order
```bash
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo.yaml
kubectl apply -f webapp.yaml
```

To monitor the deployment you can run
```bash
kubectl get all
```

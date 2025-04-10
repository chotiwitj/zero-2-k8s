# List of commands we will run through in this workshop

# Zero to K8s Workshop Command Checklist Killercoda

```bash
# Pull an image
docker run hello-world

# Save the image locally (Slide 15)
docker save nginx > nginx.tar

# Check running containers
docker ps

```
---

## 🚀 2. Kubernetes Basics – Pods & Deployments

### Create Pods – Imperative and Declarative
```bash

kubectl version

kubectl cluster-info

kubectl get nodes

kubectl create deployment nginx-deployment --image=nginx --replicas=3

kubectl get deploy

kubectl get po

k delete po nginx-deployment-xxxxx

k get po

kubectl expose deployment nginx-deployment --port=80 --type=NodePort --name=nginx-service

k get svc nginx-service -o wide
<note the ipaddress under cluster-ip>

curl localhost:Nodeport
curl <ipaddress>

k get po --show-labels

kubectl run nginx=pod --image=nginx

kubectl expose po nginx-pod --port=80 --type=NodePort --name=nginx-po

k get svc nginx-po -o wide
<note the ipaddress under cluster-ip>

curl localhost:Nodeport
curl <ipaddress>

## NOW YOUR TURN to create ##

CRI
k get nodes -o wide

CNI/CSI
k get po -A
```

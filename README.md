# 🎓 Zero to Kubernetes 

Sign up for account in [killercoda](https://killercoda.com/login).

The session is free for 4 hours!

## Hand - Dandy guide

The [list of commands](https://github.com/MG40/zero-2-k8s/blob/main/ls-commands.md) that we will run through. 

## Challenge - Imperative

It's [imperative](https://github.com/MG40/zero-2-k8s/blob/main/imperative.md) you do it now. 

##– Certificate Puzzle

Deploy your own certificate app and earn your personalized Kubernetes certificate!

## 🧩 The Challenge - Declarative - Let the controller handle it!

You’ve been given two incomplete Kubernetes manifests:

- `pod.yaml` – defines a Pod that serves your certificate
- `service.yaml` – exposes it via NodePort

Your task is to:
- Fill in all the missing values marked with `# 🔍`
- Apply both manifests to your Minikube/K8s cluster
- Open the exposed service in your browser

If everything is correct, you’ll be rewarded with your name on an official-looking certificate 🏆

## 🚀 How to Run

```bash
kubectl apply -f pod.yaml
kubectl apply -f service.yaml
minikube service <service-name>

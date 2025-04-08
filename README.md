# 🎓 Zero to Kubernetes – Certificate Puzzle

Deploy your own certificate app and earn your personalized Kubernetes certificate!

## 🧩 The Challenge

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
minikube service zero2k8s

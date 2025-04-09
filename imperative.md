# Kubernetes Imperative Commands for Zero to Kubernetes Workshop

This guide walks through the **imperative commands** needed to complete the "Zero to Kubernetes" workshop using the `gmadhavi/zero-to-k8s` image. These steps help you launch the pod, expose it via a service, and pass in a custom participant name.

---

## 🟢 Step 1: Run the Pod
```bash
kubectl run cert-pod \
  --image=gmadhavi/zero-to-k8s \
  --port=<port> \
  --env="NAME=<YourName>"
```
Replace `YourName` with your actual name.

💡 Hint: This app is based on Node.js. If you're not specifying a port, it typically listens on port 3000 by default.
---

## 🌐 Step 2: Expose the Pod via NodePort
```bash
kubectl expose pod cert-pod \
  --port=<port> \
  --target-port=<port> \
  --type=NodePort \
  --name=cert-service
```

---

## 🔎 Step 3: Get the Service Details
```bash
kubectl get svc cert-service
```
Example output:
```
NAME           TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
cert-service   NodePort   <ip-address>    <none>        3000:<nodeport>/TCP   10s
```
Take note of the NodePort (e.g., `31234`).

---

## 🧪 Step 4: Access the App via curl
```bash
curl http://localhost:<nodeport>
curl http://ip-address:<port>
```
Example:
```bash
curl http://localhost:31234
curl http://10.111.132.247:3000
```
Expected output:
```
!!! Congratulations on completing the Workshop !!!

Participant: YourName
Workshop:    Zero to Kubernetes
Date:        <today’s date>

Well done!!
```

---

## 🧠 One-Liner for the Proficient
If you're comfortable with imperative commands and want to do everything in one go:
```bash
kubectl run cert-cli \
  --image=gmadhavi/zero-to-k8s \
  --env="NAME=<YOURNAME>" \
  --port=<port> \
  --expose
```
> This creates the pod and exposes it as a `ClusterIP` service in one command. You can manually convert the service to `NodePort` if external access is needed.

---

## 📌 Notes
- These commands assume a **single-node cluster** like `kubeadm`, `minikube`, or `kind`.
- `NodePort` makes the pod accessible via the host machine’s IP or `localhost`.
- You don’t need to use the pod IP or ClusterIP to access it.

---

## 📎 Optional Cleanup
```bash
kubectl delete pod cert-pod
kubectl delete svc cert-service
```

---

## 🧠 Bonus
To list the environment variables passed to the pod:
```bash
kubectl exec cert-pod -- printenv 
```
You’ll see `NAME=YourName` in the output.


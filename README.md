
# Nginx-k8s-nodeport

## Project Structure

Your project is organized for clarity and best practices:

```
NGINX K8S/
│
├── k8s-manifests/         # All your YAML files for Kubernetes
│   ├── nginx-deployment.yaml
│   ├── nginx-service.yaml
│   ├── nginx-configmap.yaml
│   └── nginx-index.html
│
├── screenshots/           # All your screenshots
│   ├── homepage.png       # Shows the custom NGINX homepage
│   └── kube-status.png    # Shows Minikube service status output
│
└── README.md              # Your documentation
```

---

## Screenshots

### 1. NGINX Homepage
This screenshot shows the custom homepage you created for NGINX. It proves your deployment works and looks great!

![Fancy NGINX Homepage](https://github.com/inaadem/nginx-k8s-nodeport/blob/main/screenshots/homepage.png)


**What you see:**
- The page says "Welcome to Fancy NGINX! 🚀"
- Custom HTML and CSS running inside a Kubernetes pod.
- NodePort makes it accessible from your browser.

### 2. Minikube Service Status
This screenshot shows the output of the `minikube service nginx-service` command. It confirms your service is running and accessible.

![Minikube Service Output](https://github.com/inaadem/nginx-k8s-nodeport/blob/main/screenshots/kube-status.png)

**What you see:**
- Service name, target port, and the URL to access your app.
- Cluster IP and local tunnel URL (for Windows Docker driver).
- Proof that your NodePort service is working and Minikube is forwarding traffic.

**Explanation:**
- Displays the service name, target port, and the URL to access your app.
- Shows both the cluster IP and the local tunnel URL (for Windows Docker driver).
- Proves your NodePort service is working and Minikube is forwarding traffic.

---

## Table of Contents
- [Intro to K8s](#intro-to-k8s)
- [K8s Architecture](#k8s-architecture)
- [Creating a Cluster](#creating-a-cluster)
- [Deployments](#deployments)
- [Pods](#pods)
- [ReplicaSets](#replicasets)
- [Services](#services)

---

## Intro to K8s
Kubernetes (K8s) is like a game manager for your apps. It helps you run, fix, and scale your apps easily, even if your computer crashes. It’s used by big companies and students alike to keep websites and apps online and fast.

---

## K8s Architecture
Kubernetes has two main parts:

### 1. Master (Control Plane)
- **kube-apiserver**: The boss! Talks to everything in the cluster.
- **etcd**: The memory. Stores all the cluster data.
- **kube-scheduler**: Decides which worker runs which app.
- **cloud-controller-manager**: Connects K8s to cloud services.
- **kube-controller-manager**: Makes sure everything is running as it should.

### 2. Node (Worker)
- **kubelet**: The worker robot. Runs your apps (pods).
- **kube-proxy**: The traffic cop. Sends network traffic to the right place.
- **Pods**: The boxes where your app lives. Each pod can have one or more containers (like NGINX).

#### Example:
- **Node 1**: kubelet, kube-proxy, 2 pods
- **Node 2**: kubelet, kube-proxy, 1 pod

---

## Creating a Cluster
A cluster is a group of computers (nodes) managed by Kubernetes. You can create a cluster using Minikube (for learning) or in the cloud (for real apps).

---

## Deployments
A Deployment is like a blueprint. It tells K8s how many copies of your app to run and keeps them healthy. If one crashes, K8s restarts it automatically.

---

## Pods
Pods are the smallest unit in K8s. Each pod runs one or more containers (like NGINX). Pods are created, managed, and deleted by K8s as needed.

---

## ReplicaSets
ReplicaSets make sure you always have the right number of pods running. If one pod dies, ReplicaSet creates a new one.

---

## Services
Services let your app talk to the outside world or to other apps inside K8s. NodePort is a type of Service that exposes your app on a specific port so you can visit it in your browser.

---

## Summary
Kubernetes is like a team of robots managing your apps. It keeps everything running, fixes problems, and lets lots of people use your app at once. With K8s, you can deploy, scale, and manage apps easily—even as a student!

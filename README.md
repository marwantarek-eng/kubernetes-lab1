# Kubernetes Lab 1: Cluster Setup & Deployments

This repository contains the documentation and proof of execution for Kubernetes Lab 1. The lab demonstrates building a Kubernetes cluster from scratch using `kubeadm`, deploying applications, and setting up a lightweight cluster using `k3s`.

## 🛠️ Lab Objectives

1. **Install Kubernetes via Kubeadm (10 points):** Set up a v1.34.6 cluster with one control-plane node and one worker node, utilizing Flannel for pod networking.
2. **Deploy an Application (10 points):** Run an Nginx deployment on the newly created cluster.
3. **Bonus Task - K3s Installation (5 points):** Replicate the cluster setup (1 server, 1 agent) using the lightweight `k3s` distribution.

---

## 🚀 Part 1 & 2: Kubeadm Cluster & Deployment

### Cluster Initialization
- Successfully provisioned two Virtual Machines.
- Initialized the control plane on the first server using `kubeadm init` (Kubernetes version `v1.34.6`).
- Deployed the **Flannel** CNI plugin to enable pod-to-pod communication.
- Joined the second server (`client1`) to the cluster as a worker node using the `kubeadm join` token.

### Application Deployment
- Created a deployment for Nginx.
- Verified that the deployment successfully rolled out 3 replicas distributed across the cluster.

**Proof of Execution:**
The following screenshot demonstrates:
1. Three Nginx pods running successfully (`READY 1/1`, `STATUS Running`).
2. Both nodes (`localhost.localdomain` as control-plane and `client1` as worker) are in the `Ready` state running version `v1.34.6`.

<img width="618" height="185" alt="Screenshot 2026-03-31 115144" src="https://github.com/user-attachments/assets/86656b60-b928-4ce1-8e57-350e98b8992d" />
---

## 🌟 Bonus: K3s Lightweight Cluster Setup

For the bonus objective, the environment was re-provisioned using **k3s**, a highly available, certified Kubernetes distribution designed for production workloads in resource-constrained environments.

### K3s Implementation
- Installed the K3s server on the control-plane node.
- Retrieved the node token and successfully joined the `client1` agent node.

**Proof of Execution:**
The screenshot below confirms both nodes are in the `Ready` state. The version column explicitly shows `v1.34.6+k3s1`, verifying that the lightweight `k3s` distribution was used for this setup.
<img width="664" height="71" alt="Screenshot 2026-03-31 115213" src="https://github.com/user-attachments/assets/eca9fbb4-ffea-4dc4-a16a-c732f5d91cef" />


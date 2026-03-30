# Kubernetes Nginx Deployment Lab 🚀

## Overview
This project demonstrates the deployment of a highly available Nginx web server on a custom 2-node Kubernetes cluster (v1.34.6) built from scratch on Red Hat-based Linux.

## Architecture
* **Control Plane:** 1 Master Node (IP: 192.168.70.128)
* **Workers:** 1 Worker Node (IP: 192.168.70.129)
* **Container Runtime:** containerd
* **Network Plugin (CNI):** Flannel
* **Application:** Nginx (3 Replicas)

## How to Deploy
To run this deployment on the cluster, execute:
<img width="621" height="194" alt="image" src="https://github.com/user-attachments/assets/be8eaea0-173b-4178-b25e-11b3fa226baa" />

```bash
kubectl apply -f nginx-deployment.yaml

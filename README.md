# Voting-App-Deployment-on-Minikube-and-OpenShift
This repository contains Kubernetes/OpenShift manifests for deploying a simple voting application consisting of:  A frontend voting interface  A Redis queue for processing votes  A worker process for votes  A PostgreSQL database for storage  A results display interface
# 🗳️ Kubernetes Voting App

A microservices-based voting application deployed using Kubernetes. This project demonstrates deploying a full-stack app consisting of frontend, backend, Redis, PostgreSQL, and message queueing with worker logic using Kubernetes concepts such as Deployments, Services, StatefulSets, Secrets, and Ingress.

## 📦 Project Structure

This system is composed of the following components:

- **vote** – Frontend voting app written in Python/Flask
- **result** – Frontend result app written in Node.js
- **worker** – Backend processor for Redis queue (uses .NET Core)
- **redis** – In-memory data store used for message queueing
- **db (PostgreSQL)** – Relational database to store voting results
- **Ingress** – For routing external traffic
- **Secrets** – Used to store sensitive database credentials

## 🧱 Kubernetes Resources

The project uses the following Kubernetes objects:

- Deployments: `vote`, `result`, `worker`, `redis`
- StatefulSet: `db`
- Services: ClusterIP for internal communication
- Secret: Stores `POSTGRES_USER` and `POSTGRES_PASSWORD`
- Ingress: Routes traffic to `vote.example.com` and `result.example.com`

## 🚀 Getting Started

### Prerequisites

- Kubernetes Cluster (Minikube, k3s, OpenShift, etc.)
- `kubectl` or `oc` CLI
- `Ingress` controller installed (like NGINX Ingress)

### Deployment

1. **Clone the repository**
   ```bash
   git clone (https://github.com/Megs17/Voting-App-Deployment-on-Minikube-and-OpenShift)
   cd kubernetes-voting-app

2. **Apply Kubernetes resources**
   ```bash
   kubectl apply -f .
   
3. **Use minikube ingress controller**

2. **Access the app**
   ```bash
Frontend Voting: http://vote.example.com

Result Page: http://result.example.com


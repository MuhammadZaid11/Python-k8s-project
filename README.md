# Django Notes App on Kubernetes

## Project Overview

This project demonstrates how to containerize and deploy a Django Notes Application using Docker, Docker Hub, and Kubernetes.

The goal of this project is to learn and implement core Kubernetes concepts including:

* Namespace
* Deployment
* Replicas
* Labels and Selectors
* Services
* Docker Images
* Docker Hub Integration
* Pod Management

This project is part of my Kubernetes and DevOps learning journey.

---

## Architecture

```text
Docker Hub
    │
    ▼
Kubernetes Deployment
    │
    ▼
ReplicaSet
    │
 ┌──┴──┐
 ▼     ▼
Pod 1  Pod 2
   \   /
    \ /
 Service
```

---

## Project Structure

```text
django-notes-app/
│
├── api/
├── mynotes/
├── notesapp/
├── manage.py
├── requirements.txt
├── Dockerfile
│
├── k8s/
│   ├── namespace.yaml
│   ├── deployment.yaml
│   └── service.yaml
│
└── README.md
```

---

## Technologies Used

* Python
* Django
* Docker
* Docker Hub
* Kubernetes
* GitHub
* GitHub Codespaces

---

## Docker Setup

### Build Docker Image

```bash
docker build -t <dockerhub-username>/django-notes:v1 .
```

### Login to Docker Hub

```bash
docker login
```

### Push Image

```bash
docker push <dockerhub-username>/django-notes:v1
```

---

## Kubernetes Resources

### Namespace

Creates an isolated environment for application resources.

```yaml
kind: Namespace
```

### Deployment

Manages application Pods and replicas.

```yaml
kind: Deployment
```

Features:

* Self-Healing
* Scaling
* Rolling Updates
* Replica Management

### Service

Provides a stable endpoint for application access.

```yaml
kind: Service
```

---

## Deployment Steps

### Create Namespace

```bash
kubectl apply -f k8s/namespace.yaml
```

### Deploy Application

```bash
kubectl apply -f k8s/deployment.yaml
```

### Create Service

```bash
kubectl apply -f k8s/service.yaml
```

---

## Verification Commands

### Check Namespace

```bash
kubectl get ns
```

### Check Deployment

```bash
kubectl get deployment -n dev
```

### Check Pods

```bash
kubectl get pods -n dev
```

### Check Service

```bash
kubectl get svc -n dev
```

### Describe Service

```bash
kubectl describe svc django-notes-service -n dev
```

---

## Kubernetes Concepts Demonstrated

| Concept    | Description              |
| ---------- | ------------------------ |
| Namespace  | Resource Isolation       |
| Deployment | Pod Management           |
| ReplicaSet | Desired State Management |
| Replicas   | High Availability        |
| Labels     | Resource Identification  |
| Selectors  | Resource Matching        |
| Service    | Stable Networking        |
| Docker Hub | Image Registry           |
| Pods       | Application Runtime      |

---

## Learning Outcomes

After completing this project, I learned:

* How to containerize a Django application
* How Docker images are built and pushed to Docker Hub
* How Kubernetes Deployments create and manage Pods
* How Services communicate with Pods using Labels and Selectors
* How Namespaces isolate resources
* How to troubleshoot Kubernetes resources using kubectl

---

## Future Enhancements

Planned improvements:

* ConfigMaps
* Secrets
* NodePort Service
* Ingress Controller
* Horizontal Pod Autoscaler (HPA)
* GitHub Actions CI/CD
* Amazon EKS Deployment
* Monitoring with Prometheus and Grafana

---

## Author

**Muhammad Zaid**

Aspiring DevOps Engineer | Cloud Data Engineering Student | Python Developer

Currently learning:

* Kubernetes
* Docker
* AWS
* DevOps
* Cloud Technologies

[README (3).md](https://github.com/user-attachments/files/31448714/README.3.md)
# 🎮 Tic Tac Toe — DevSecOps & Kubernetes Project

A production-style **Tic Tac Toe web application** deployed using a complete DevSecOps workflow.  
The project demonstrates how a containerized application can be automatically tested, analyzed, built, deployed to Kubernetes, synchronized through Argo CD, and monitored using Grafana.

> **Project Focus:** CI/CD • Docker • Kubernetes • GitHub Actions • Argo CD • Static Code Analysis • Monitoring

---

## 🚀 Project Overview

This project takes a simple Tic Tac Toe application and turns it into a **cloud-native DevOps deployment pipeline**.

Every code change pushed to GitHub can go through the following workflow:

```text
Developer
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ├── Unit Testing
    ├── Static Code Analysis
    ├── Application Build
    └── Docker Build & Push
             │
             ▼
      Container Registry
             │
             ▼
      Kubernetes Cluster
             │
             ▼
          Argo CD
             │
             ▼
       Application Pods
             │
             ▼
       Grafana Monitoring
```

The goal is to demonstrate an automated deployment workflow rather than simply running the application locally.

---

## ✨ Key Features

- 🎮 Interactive Tic Tac Toe web application
- 🐳 Dockerized application
- 🔄 Automated CI/CD using GitHub Actions
- 🧪 Automated unit testing
- 🔍 Static code analysis
- 📦 Automated Docker image build and push
- ☸️ Kubernetes-based deployment
- 🔁 GitOps-style continuous delivery with Argo CD
- 📊 Grafana-based application/Kubernetes monitoring
- ♻️ Automated deployment updates after successful pipeline execution
- 📈 Resource monitoring for CPU and memory utilization

---

## 🛠️ Technology Stack

| Category | Technology |
|---|---|
| Application | Tic Tac Toe Web Application |
| Version Control | Git & GitHub |
| CI/CD | GitHub Actions |
| Containerization | Docker |
| Orchestration | Kubernetes |
| GitOps / CD | Argo CD |
| Code Quality | Static Code Analysis |
| Monitoring | Grafana |
| Runtime | Kubernetes Pods |
| Registry | Docker Container Registry |

---

## 🔄 CI/CD Pipeline

The GitHub Actions pipeline is divided into multiple stages:

### 1. Unit Testing

The application is tested automatically whenever changes are pushed.

```text
Code Push
   ↓
Unit Tests
   ↓
Pass / Fail
```

A failed test prevents the pipeline from continuing.

### 2. Static Code Analysis

The source code is analyzed to identify potential quality issues and maintainability problems before deployment.

### 3. Application Build

The application is built as part of the CI workflow to ensure that the submitted code can be successfully packaged.

### 4. Docker Build & Push

A Docker image is created from the application and pushed to the configured container registry.

```text
Application Source
        ↓
     Dockerfile
        ↓
   Docker Image
        ↓
Container Registry
```

### 5. Kubernetes Deployment Update

After the image is successfully published, the deployment configuration is updated so Kubernetes can run the new application version.

---

## ☸️ Kubernetes Deployment

The application runs inside a Kubernetes cluster.

The Kubernetes environment contains the application workload along with the supporting Argo CD components.

Example deployment flow:

```text
Docker Image
     ↓
Kubernetes Deployment
     ↓
Application Pods
     ↓
Kubernetes Service
     ↓
Tic Tac Toe Application
```

Kubernetes provides:

- Container orchestration
- Desired-state management
- Pod lifecycle management
- Service-based application access
- Automatic restart/reconciliation of failed workloads

---

## 🔁 Argo CD & GitOps

**Argo CD** is used for continuous delivery and GitOps-based deployment management.

The desired application state is maintained through declarative Kubernetes configuration.

Argo CD continuously compares the desired state with the state running inside the Kubernetes cluster.

```text
Git Repository
      │
      │ Desired State
      ▼
    Argo CD
      │
      ▼
 Kubernetes Cluster
      │
      ▼
 Application Pods
```

The Argo CD application dashboard provides visibility into:

- Application health
- Sync status
- Kubernetes resources
- Deployment relationships
- Application state

This makes deployment state easier to observe and manage.

---

## 📊 Monitoring with Grafana

Grafana is used to visualize Kubernetes resource utilization and application infrastructure metrics.

The monitoring dashboard provides visibility into metrics such as:

- CPU utilization
- Memory utilization
- Pod resource consumption
- Kubernetes workload metrics
- Resource usage trends over time

Example dashboard views include CPU and memory utilization across the deployed workloads.

This helps identify abnormal resource usage and provides operational visibility after deployment.

---

## 🐳 Running Locally with Docker

Clone the repository:

```bash
git clone <your-repository-url>
cd tic-tac-toe-devsecops
```

Build the Docker image:

```bash
docker build -t tic-tac-toe .
```

Run the container:

```bash
docker run -p 8081:8081 tic-tac-toe
```

Then open:

```text
http://localhost:8081
```

> Update the port if the application is configured to listen on a different port.

---

## ☸️ Deploying to Kubernetes

Apply the Kubernetes manifests:

```bash
kubectl apply -f k8s/
```

Check the deployed pods:

```bash
kubectl get pods
```

Check services:

```bash
kubectl get svc
```

Check deployments:

```bash
kubectl get deployments
```

---

## 🔍 Useful Kubernetes Commands

Check running workloads:

```bash
kubectl get pods
```

Check all resources:

```bash
kubectl get all
```

Inspect a pod:

```bash
kubectl describe pod <pod-name>
```

View application logs:

```bash
kubectl logs <pod-name>
```

Check deployment status:

```bash
kubectl rollout status deployment/<deployment-name>
```

---

## 📁 Project Structure

```text
tic-tac-toe-devsecops/
│
├── .github/
│   └── workflows/
│       └── ci-cd.yml
│
├── k8s/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ...
│
├── argocd/
│   └── application.yaml
│
├── src/
│   └── ...
│
├── Dockerfile
├── README.md
└── .gitignore
```

> The exact directory structure may vary depending on the final application source layout.

---

## 🔐 DevSecOps Practices Demonstrated

This project focuses on integrating quality and operational practices directly into the software delivery lifecycle.

### Continuous Integration

- Automated testing
- Static code analysis
- Automated builds
- Docker image creation

### Continuous Delivery

- Kubernetes deployment
- GitOps-based synchronization
- Argo CD application management

### Observability

- Grafana dashboards
- CPU and memory monitoring
- Kubernetes workload visibility

---

## 🎯 What I Learned

Through this project, I gained practical experience with:

- Designing a CI/CD workflow using GitHub Actions
- Containerizing applications with Docker
- Deploying workloads to Kubernetes
- Managing Kubernetes resources
- Implementing GitOps using Argo CD
- Integrating automated testing into CI
- Using static analysis as part of the development pipeline
- Monitoring Kubernetes workloads using Grafana
- Troubleshooting container, networking, deployment, and resource issues
- Understanding the flow from source code → container → Kubernetes → GitOps → monitoring

---

## 📸 Project Screenshots

### Application

The Tic Tac Toe application running as a deployed web application.

### GitHub Actions

CI/CD pipeline showing:

```text
Unit Testing
     ↓
Static Code Analysis
     ↓
Build
     ↓
Docker Build & Push
     ↓
Kubernetes Deployment Update
```

### Argo CD

Argo CD dashboard showing the application synchronized and healthy inside the Kubernetes cluster.

### Grafana

Grafana dashboard showing Kubernetes CPU and memory utilization.

---

## 🏆 Resume Project Summary

**Tic Tac Toe — DevSecOps & Kubernetes Deployment**

Built and deployed a containerized Tic Tac Toe application using **Docker, Kubernetes, GitHub Actions, and Argo CD**, implementing automated testing, static code analysis, Docker image delivery, GitOps-based deployment synchronization, and **Grafana-based Kubernetes monitoring**.

---

## 👨‍💻 Author

**Hardik Garg**

Built as a hands-on DevOps / Cloud Engineering project to demonstrate an end-to-end application delivery and monitoring workflow.

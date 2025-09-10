DevOps Platform on Kubernetes
A production-grade, self-service internal developer platform built on Minikube. This project demonstrates a complete GitOps workflow, from code commit to production deployment, featuring full CI/CD automation, monitoring, and environment isolation.

📋 Table of Contents

Features
Tech Stack
Prerequisites
Project Structure
CI/CD Pipeline
Monitoring
Learning Journey

✨ Features
✅ Full CI/CD Automation - From code push to production deployment
✅ Multi-Environment Deployment - Isolated staging and production namespaces
✅ Self-Hosted GitHub Runners - Fast, secure builds on WSL2 infrastructure
✅ Infrastructure as Code - Helm charts for templated Kubernetes manifests
✅ Monitoring Stack - Prometheus and Grafana for observability
✅ Security Scanning - Container vulnerability scanning in pipeline
✅ Zero-Downtime Deployments - Rolling updates with health checks

🛠️ Tech                       Stack
Component	                    Technology
Container                     Orchestration	Kubernetes (Minikube)
CI/CD	                        GitHub Actions (Self-Hosted Runners)
Containerization	            Docker
Package Management	          Helm
Container Registry	          Docker Hub
Ingress Controller	          NGINX Ingress
Monitoring	                  Prometheus + Grafana

📋 Prerequisites
Before you begin, ensure you have the following installed:
Minikube (v1.0.0+)
kubectl (v1.25+)
Helm (v3.0+)
Docker (v20.0+)
GitHub Runner (configured on WSL2)

📁 Project Structure
├── .github/
│   └── workflows/
│       └── main.yml              # CI/CD Pipeline
├── helm/
│   └── youssefsapp/
│       ├── Chart.yaml
│       ├── values.yaml
│       ├── values-staging.yaml
│       ├── values-production.yaml
│       └── templates/
│           ├── deployment.yaml
│           ├── service.yaml
│           ├── ingress.yaml
│           └── _helpers.tpl
├── backapp/                      # Backend application
│   ├── Dockerfile
│   ├── package.json
│   └── index.js
├── frontapp/                     # Frontend application
│   ├── Dockerfile
│   ├── nginx.conf
│   └── beginner-html-site-styled/
└── README.md

🔄 CI/CD Pipeline
The GitHub Actions workflow provides:
Build Stage: Docker image building and vulnerability scanning
Test Stage: (Optional) Application testing
Deploy Stage: Automated deployment to staging
Promotion: Manual approval for production deployment

Pipeline Features:
Self-hosted runners for faster execution
Vulnerability scanning with Trivy
Environment-specific configurations
Rolling deployments with health checks

🎓 Learning Journey
This project was built to master:
Kubernetes architecture and operations
Helm chart development and templating
CI/CD pipeline design and implementation
Production-ready deployment strategies
Monitoring and observability practices

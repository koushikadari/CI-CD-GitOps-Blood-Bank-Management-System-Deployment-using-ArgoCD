# CI-CD-GitOps-Blood-Bank-Management-System-Deployment-using-ArgoCD
CI/CD &amp; GitOps: Blood Bank Management System Deployment using ArgoCD

🎯 Objective

> To automate the entire software lifecycle using:

@ Jenkins for Continuous Integration (CI)

@ Docker for containerization

@ SonarQube for code quality analysis

@ Trivy for image vulnerability scanning

@ DockerHub for image storage

@ Kubernetes (via Kops) for container orchestration

@ ArgoCD for Continuous Deployment (CD) with GitOps principles


🧱 Step 1: Jenkins Instance Setup

# An EC2 instance (2 CPUs, 8 GB RAM) is launched to act as the CI server.
> Jenkins is installed and configured along with:

@ Docker (to build container images)

@ SonarQube (for code quality)

@ Trivy (for container security scanning)

# Required Jenkins plugins:

@ Pipeline: Stage View

@ SonarQube Scanner

@ Docker Pipeline

The instance also has an IAM Role attached, so it can access AWS resources securely.

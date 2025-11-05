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


# 🧱 Step 1: Jenkins Instance Setup

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

# 🧪 Step 2: Jenkins CI Pipeline Process

The Jenkins pipeline automates the entire CI process.
Here’s what each stage does:

 # Clean Workspace:
 Removes old files to ensure a fresh build environment.

# Checkout Code:
Pulls the source code from a GitHub repository.

# SonarQube Analysis (SQA):
Uses SonarQube to analyze code for bugs, vulnerabilities, and code smells.

# Quality Gate Check:
Verifies the SonarQube analysis result — if the quality standards fail, the pipeline can be stopped or marked unstable.

# Docker Image Build:
Builds Docker images for both the application and the database from the source code.

# Trivy Image Scan:
Scans the built Docker images for vulnerabilities.

# Push to DockerHub:
Pushes the final, approved images to a DockerHub repository for deployment.

# 🧰 Step 3: Kops and Kubectl Setup 

A separate EC2 instance acts as the Kubernetes admin node.
It has:

Kubectl: to manage Kubernetes resources

Kops: to create and manage the Kubernetes cluster on AWS

The Kubernetes cluster is created using Kops, consisting of:

@ Master node

@ Worker nodes

@ used this command for to create kops cluster ==  kops create cluster --name koushik.k8s.local --zones=us-east-1a,us-east-1b --master-count=1 --master-size=m7i.large --master-volume-size=30  --node-count=2 --node-size=c7a.large --node-volume-size=20 --image=ami-0360c520857e3138f

Appropriate instance types and storage sizes

This cluster hosts the application and all associated services.








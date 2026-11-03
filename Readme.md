# 🛡️ Enterprise Cloud Security Operations Platform

An enterprise-focused cloud security project built around **OWASP Juice Shop**, an intentionally vulnerable web application. The project explores how to deploy, secure, monitor, and protect application workloads using **Google Cloud Platform (GCP), Kubernetes, Infrastructure as Code (IaC), and DevSecOps practices.**

## 📌 Project Overview

Modern cloud environments require more than simply deploying applications. They need layered security controls, continuous vulnerability assessment, secure deployment pipelines, threat detection, and incident response capabilities.

This project aims to build an **Enterprise Cloud Security Operations Platform** that demonstrates these capabilities using OWASP Juice Shop as the application workload.

The implementation will progressively introduce cloud infrastructure, security controls, automated security testing, monitoring, and incident response.

## 🎯 Project Objectives

- ☁️ Deploy and manage containerised application workloads.
- 🏗️ Implement Infrastructure as Code using Terraform.
- 🔐 Apply Zero Trust principles and least-privilege access.
- 🔍 Implement container vulnerability scanning and application security testing.
- ⚙️ Build automated DevSecOps pipelines.
- ☸️ Deploy and secure workloads on Google Kubernetes Engine (GKE).
- 🚨 Implement security monitoring, threat detection, and automated response.
- 📊 Develop security posture reporting and visibility.

## 🧰 Technology Stack

| Category | Technologies |
|:---|:---|
| Application | OWASP Juice Shop |
| Containers | Docker |
| Orchestration | Kubernetes, GKE |
| Cloud Platform | Google Cloud Platform |
| Infrastructure as Code | Terraform |
| CI/CD | GitHub Actions |
| Vulnerability Scanning | Trivy |
| Application Security Testing | OWASP ZAP |
| Security Monitoring | Security Command Center, Cloud Logging |
| Automation | Python, Eventarc, Pub/Sub |
| Reporting | BigQuery, Looker Studio |

*Technologies will be introduced progressively as the project develops.*

## 🚀 Current Implementation

### Phase 1: Local Application Deployment

- 📦 Obtained the OWASP Juice Shop Docker image.
- 🐳 Created and ran a Docker container.
- 🔌 Configured port mapping to access the application locally.
- 🔎 Inspected container status and logs.
- 🔄 Practised stopping and restarting containers.

### ▶️ Run Locally

**1. Pull the application image**

```bash
docker pull bkimminich/juice-shop
```

**2. Run the container**

```bash
docker run -d -p 3000:3000 --name juice-shop bkimminich/juice-shop
```

**3. Access the application**

Open your browser and navigate to:

```text
http://localhost:3000
```

**4. Check running containers**

```bash
docker ps
```

**5. View all containers**

```bash
docker ps -a
```

**6. View container logs**

```bash
docker logs juice-shop
```

**7. Stop and restart the container**

```bash
docker stop juice-shop
docker start juice-shop
```

## 🗺️ Planned Implementation Roadmap

1. 🐳 Local application and Docker deployment.
2. ☸️ Container lifecycle and Kubernetes fundamentals.
3. 🔍 Application vulnerability assessment.
4. ⚙️ DevSecOps pipeline and automated security scanning.
5. 🏗️ Terraform infrastructure provisioning.
6. 🌐 GCP networking and IAM security.
7. ☁️ GKE deployment and workload protection.
8. 🔐 Application protection and secrets management.
9. 🚨 Security monitoring and automated incident response.
10. 📊 Security posture reporting and documentation.

## ⚠️ Security Considerations

OWASP Juice Shop is intentionally vulnerable and is used as a controlled security testing workload.

It should only be exposed in controlled testing environments. It must not be deployed publicly without appropriate isolation and protective controls.

## 📈 Project Status

**Status:** 🚧 In Progress

This repository documents the architecture, implementation, security decisions, challenges, troubleshooting, and lessons learned throughout the project.
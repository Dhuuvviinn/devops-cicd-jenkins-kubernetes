# BoardGame – End-to-End DevOps CI/CD Project

![DevOps CI/CD Pipeline](IMAGES/devops-cicd-jenkins-k8s-aws.png)

Production-grade CI/CD pipeline for a Java application using Jenkins, Docker, Kubernetes, AWS, and full monitoring with Prometheus & Grafana.

---

## CI/CD Pipeline Overview

### Pipeline Stages
- 🐙 GitHub (main branch)
- ☕ Maven Compile & Test
- 🔍 Trivy File System Scan
- 📊 SonarQube Code Analysis
- 🚦 Quality Gate Enforcement
- 📦 Nexus Artifact Deployment
- 🐳 Docker Build & Tag
- 🛡️ Trivy Image Scan
- 🚀 Docker Hub Push
- ☸️ Kubernetes Deployment
- ✅ Deployment Verification
- 📧 Email Notification with Reports

📄 **Pipeline definition:** [View Jenkinsfile](Jenkinsfile)

---

## Jenkins Pipeline Execution

![Jenkins Stage View](IMAGES/jenkins-stage-view.png)

---

## AWS Infrastructure

![AWS EC2](IMAGES/aws-ec2-instances.png)

### EC2 Instances
- Jenkins (t2.large)
- Kubernetes Cluster: 1 Master + 2 Workers
- SonarQube
- Nexus
- Monitoring (Prometheus + Grafana + Blackbox Exporter)

**Region:** `us-east-2`

---

## Monitoring & Observability

### Grafana – Service Health
![Grafana Dashboard](IMAGES/Grafana.png)

### Prometheus Targets
![Prometheus Targets](IMAGES/prometheus.png)

### Blackbox Exporter
![Blackbox Exporter](IMAGES/Blackbox_Exporter.png)

---

## Application UI

![Application UI](IMAGES/Boardgame.png)

---

## Notifications

Automated email notification sent after every pipeline execution with Trivy HTML vulnerability report attached.

![Email Notification](IMAGES/Email-notification.png)

---

## Security & Quality

- Trivy File System & Docker Image scanning
- SonarQube Quality Gates enforcement
- Artifact versioning and storage via Nexus
- Secrets stored using environment variables
- No credentials committed to the repository
- Role-based access control across services

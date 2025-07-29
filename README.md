📺 DevSecOps Netflix Clone Deployment on EKS
Overview
This repository contains all necessary code, scripts, and infrastructure-as-code templates to deploy a Netflix‑like application on Kubernetes (AWS EKS) using a security-first DevSecOps pipeline.

The pipeline integrates automated scanning, vulnerability checks, and deployment workflows—designed for continuous delivery with complete security compliance.

🔧 Features
Infrastructure provisioning with Terraform/CloudFormation

CI/CD pipeline configured using Jenkins/GitHub Actions/CodePipeline

Container scanning (e.g. Trivy, Clair)

Static application security testing (SAST)

Dynamic application security testing (DAST) into deployment flow

Kubernetes deployment files for services, ingress, config maps

Automated rollback & secret management following best practices

Monitoring & alerting via Prometheus and Grafana or AWS CloudWatch



🚀 Getting Started
Prerequisites
AWS CLI, Kubectl

Terraform or AWS CloudFormation

CI/CD tools (e.g. Jenkins, GitHub Actions)

Container vulnerability scanners: Trivy, Clair

SAST/DAST tools (e.g. SonarQube, OWASP ZAP)

Docker, AWS IAM permissions

Installation & Deployment
Clone this repository:


git clone https://github.com/azharshaikh7898/netflix‑clone.git
cd netflix‑clone‑
Provision infrastructure:

cd infra/
terraform init
terraform apply
Or run the CloudFormation stack if using AWS templates.

Build & scan application images:

docker build -t netflix-clone:latest .
trivy image netflix-clone:latest
Configure CI/CD pipeline credentials (e.g. AWS keys, connection tokens).

Push changes, triggering automated pipeline:

Containers are scanned

Security report generated

If clear, deployment to AWS EKS cluster

🛡️ DevSecOps Pipeline Flow
Stage	Tool(s)	Purpose
Code Build	Docker, Maven/Gradle	Build and assemble application
Static Analysis	SonarQube, ESLint	Detect coding standards and security issues
Container Scanning	Trivy or Clair	Check for CVEs in container dependencies
Dynamic Testing	OWASP ZAP or similar	Simulate runtime vulnerabilities
Deployment	Terraform / kubectl	Provision infra and deploy to cluster
Monitoring	Prometheus, Grafana or CloudWatch	Observe app behavior and logs

📦 Folder Structure
bash
Copy
Edit
.
├── infra/                 # Infrastructure-as-code templates
├── pipeline/              # CI/CD configuration files
├── app/                   # Application source code
├── docker/                # Dockerfiles and container scripts
└── kubernetes/            # K8s manifests & Helm charts
✅ Success Criteria
Fully functional microservices up and running on AWS EKS

Security scan results (SAST & container scan) in pipeline logs/artifacts

Fail-on-error policy for scans: builds don't pass insecure releases

Alerts and dashboards show healthy uptime and metrics

🧪 Testing
Unit test suites for backend/frontend code

Security scan report validation

End-to-end smoke tests post-deployment

Load testing scenarios (optional)


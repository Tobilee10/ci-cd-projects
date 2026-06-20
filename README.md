# ⚙️ GitHub Actions CI/CD Engine

A centralized, production-grade repository of Continuous Integration and Continuous Deployment (CI/CD) pipelines engineered with GitHub Actions. This repository serves as a comprehensive DevOps portfolio, demonstrating enterprise-level automation, containerization strategies, DevSecOps infrastructure, and GitOps-driven cloud deployments.

By utilizing a monorepo architecture, each project operates as an isolated pipeline managed through GitHub Actions path-filtering mechanics—ensuring zero workflow cross-interference and optimized runner execution times.

---

## 🛠️ Global Engineering Stack

* **CI/CD Platform:** GitHub Actions (YAML workflow orchestration)
* **Containerization & Orchestration:** Docker, Docker Compose, Kubernetes
* **Security & Quality:** Trivy, SonarQube, Hadolint, Flake8, Pytest
* **Infrastructure as Code (IaC):** Terraform
* **Cloud & Target Environments:** AWS, Google Cloud Platform (GCP), Ubuntu/Linux Runners
* **Languages & Automation:** Python (FastAPI), Bash/Shell Scripting, Nginx Configuration

---

## 📂 Architecture & Pipeline Directory

### 📦 Tier 1: Core Automation & Linux Administration
*Demonstrating fundamental operating system automation and quality gates.*

#### 1. Dockerized Static Website Pipeline
* **Directory Path:** [`/dockerised-static-website-pipeline`](./dockerised-static-website-pipeline)
* **Objective:** Automate the multi-stage build and delivery lifecycle of a secure, lightweight static web server.
* **Key Mechanisms:** Dockerfile linting via `hadolint`, path-filtering execution isolation, and image deployment optimization.

#### 2. Automated System Log Rotator & Backup Script
* **Directory Path:** [`/linux-log-backup-automation`](./linux-log-backup-automation)
* **Objective:** Orchestrate system-level maintenance operations via scheduled automated tasks.
* **Key Mechanisms:** Event-driven execution utilizing GitHub Actions `schedule` cron triggers, automated bash syntax verification, and secure cloud archiving.

#### 3. Automated Python API Linting & Unit Testing Engine
* **Directory Path:** [`/fastapi-ci-test-suite`](./fastapi-ci-test-suite)
* **Objective:** Implement a strict, early-stage continuous integration quality gate for backend codebases.
* **Key Mechanisms:** Automated execution of `flake8`/`black` for style uniformity, `mypy` for static type checking, and `pytest` test-coverage enforcement.

---

### 📦 Tier 2: Containerization & Local Orchestration
*Demonstrating multi-container networks, optimized builds, and registry management.*

#### 4. Optimized Multi-Stage FastAPI & PostgreSQL Stack
* **Directory Path:** [`/containerized-fastapi-postgres`](./containerized-fastapi-postgres)
* **Objective:** Compile and distribute secure, minimal production container images for relational applications.
* **Key Mechanisms:** Multi-stage Docker optimization to strip compilation layers, semantic image version tagging, and automated pushes to Docker Hub.

#### 5. Redis Cache & Nginx Reverse Proxy Engine
* **Directory Path:** [`/nginx-redis-reverse-proxy`](./nginx-redis-reverse-proxy)
* **Objective:** Validate network proxy routing and caching architecture configurations automatically.
* **Key Mechanisms:** Runner-level `docker-compose` orchestration, automated curl-based HTTP reverse proxy health checking, and container network validation.

#### 6. Microservices Inventory Management Stack (Telusko Trac)
* **Directory Path:** [`/telusko-trac-microservices`](./telusko-trac-microservices)
* **Objective:** Orchestrate a complex integration and deployment matrix for decoupled multi-tier web applications.
* **Key Mechanisms:** Parallelized multi-image container building, isolated virtual Docker network testing, and dynamic Git commit SHA-to-image mapping.

---

### 📦 Tier 3: DevSecOps (Shift-Left Security)
*Demonstrating automated vulnerability assessment and continuous quality gates.*

#### 7. Container & Dependency Vulnerability Scanner
* **Directory Path:** [`/devsecops-trivy-scanner`](./devsecops-trivy-scanner)
* **Objective:** Prevent vulnerable operating system layers and open-source packages from infiltrating registries.
* **Key Mechanisms:** **Trivy** vulnerability matrix scanning embedded inside the runner, package manifest inspection, and hard-failing builds on "High" or "Critical" CVE flags.

#### 8. Static Application Security Testing (SAST) with SonarQube
* **Directory Path:** [`/sast-sonarqube-pipeline`](./sast-sonarqube-pipeline)
* **Objective:** Evaluate deep code-quality issues, security hotspots, and technical debt prior to main branch merging.
* **Key Mechanisms:** SonarCloud code scanning, quality-gate baseline enforcement, and automated analysis reporting.

---

### 📦 Tier 4: Advanced GitOps & Cloud Deployments
*Demonstrating cloud provision automation, serverless operations, and declarative state orchestration.*

#### 9. Infrastructure as Code (IaC) Provisioning with Terraform
* **Directory Path:** [`/terraform-cloud-provisioning`](./terraform-cloud-provisioning)
* **Objective:** Automate infrastructure state validation and cloud resource planning.
* **Key Mechanisms:** Automated `terraform validate`, automated plan generation on Pull Requests, and state execution upon branch merges.

#### 10. Serverless Cloud Run Continuous Deployment Pipeline
* **Directory Path:** [`/cloudrun-serverless-cd`](./cloudrun-serverless-cd)
* **Objective:** Ship applications into scalable cloud-native architectures securely and reliably.
* **Key Mechanisms:** **OpenID Connect (OIDC)** authentication (keyless authentication architecture), artifact generation, and zero-downtime deployment to GCP Cloud Run / AWS ECS.

#### 11. ArgoCD GitOps Engine (Kubernetes Orchestration)
* **Directory Path:** [`/k8s-argocd-gitops`](./k8s-argocd-gitops)
* **Objective:** Drive cloud state configuration deterministically using declarative manifests.
* **Key Mechanisms:** Manifest mutation via automated workflow commits, version tag automation, and declarative drift reconciliation via an ArgoCD controller model.

---

## 🧠 Monorepo Pipeline Isolation Strategy

To ensure workflows scale cleanly without interfering with adjacent projects, every configuration file inside `.github/workflows/` relies on **strict path-filtering execution gates**:

```yaml
on:
  push:
    branches: [ main ]
    paths:
      - 'dockerised-static-website-pipeline/**' # Ensures this pipeline ONLY runs when changes occur in this specific directory
```
## Repository File Mapping:
Because multiple projects live under this single engine, workflows are managed centrally but executed independently:Because multiple projects live under this single engine, workflows are managed centrally but executed independently:

Because multiple projects live under this single engine, workflows are managed centrally but executed independently:

Because multiple projects live under this single engine, workflows are managed centrally but executed independently:

Because multiple projects live under this single engine, workflows are managed centrally but executed independently:



github-actions-cicd-engine/
├── .github/
│   └── workflows/
│       ├── static-website-ci.yml
│       ├── fastapi-tests-ci.yml
│       └── [additional-workflows].yml
├── dockerised-static-website-pipeline/
├── linux-log-backup-automation/
├── ... [other project directories]
└── README.md

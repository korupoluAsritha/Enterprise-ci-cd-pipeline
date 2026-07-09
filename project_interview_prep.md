# Enterprise CI/CD Project Interview Preparation

# Project Summary

Built a CI/CD pipeline using:

- GitHub
- Jenkins
- Python
- Flask
- Pytest
- Docker

Pipeline automates:

- Source retrieval
- Dependency installation
- Unit testing
- Docker image creation
- Application deployment
- Health validation

---

# Architecture

```text
GitHub
   |
Jenkins
   |
Environment Validation
   |
Git Clone
   |
Dependency Installation
   |
Pytest
   |
Docker Build
   |
Deployment
   |
Health Check
```

---

# Explain Jenkins Workspace

A workspace is a dedicated directory where Jenkins stores source code and executes build steps.

Example:

```text
C:\ProgramData\Jenkins\.jenkins\workspace
```

---

# Explain CI

Continuous Integration validates every change.

Activities:

```text
Build
Test
Validate
```

Goal:

Detect issues early.

---

# Explain CD

Continuous Delivery automates deployment after successful validation.

Activities:

```text
Deploy
Verify
```

---

# Explain Docker Image

Immutable application package.

Contains:

- Application code
- Runtime
- Dependencies

Example:

```bash
docker build -t flask-app:9 .
```

---

# Explain Container

Running instance of image.

Example:

```bash
docker run flask-app:9
```

---

# Explain Build Number

Jenkins automatically provides:

```text
BUILD_NUMBER
```

Used to create:

```text
flask-app:9
```

Benefits:

- Traceability
- Rollback
- Auditing

---

# Explain Fail Fast

Pipeline order:

```text
Tests
   |
Docker Build
   |
Deploy
```

instead of:

```text
Deploy
   |
Find Failure Later
```

---

# Explain Health Checks

Health checks confirm application availability after deployment.

Example:

```cmd
curl http://localhost:5000
```

Benefits:

```text
Container Running ≠ Application Healthy
```

---

# Explain Docker Cache

Docker stores image layers.

Repeated builds reuse unchanged layers.

Benefits:

- Faster builds
- Reduced downloads
- Better CI performance

---

# Real Troubleshooting Examples

## Jenkins Plugin Issue

Finding:

```text
82 .jpi.tmp files
```

Root Cause:

Incomplete plugin downloads.

Impact:

Pipeline functionality unavailable.

---

## pytest Issue

Error:

```text
pytest not recognized
```

Fix:

```cmd
python -m pytest
```

---

## Shell Issue

Error:

```text
Cannot run program "sh"
```

Root Cause:

Linux shell command used on Windows.

Fix:

```text
Execute Windows batch command
```

---

# Why This Project Matters

This project demonstrates:

- CI implementation
- CD implementation
- Docker containerization
- Automated testing
- Deployment automation
- Health validation
- Root Cause Analysis
- Troubleshooting methodology

rather than only tool installation.

---

# Future Enterprise Architecture

```text
GitHub
    |
GitHub Webhook
    |
Jenkins Pipeline
    |
Unit Tests
    |
Security Scans
    |
Docker Build
    |
Docker Hub
    |
Kubernetes
    |
Prometheus
    |
Grafana
```

---

# Elevator Pitch

I built an end-to-end CI/CD platform using GitHub, Jenkins, Docker, Flask, and Pytest. The pipeline automatically retrieves source code, validates dependencies, executes automated tests, builds versioned Docker images, deploys containers, and performs health verification. Throughout the project I focused heavily on troubleshooting and root cause analysis, resolving issues related to Git workflows, Docker architecture, Jenkins execution environments, plugin dependency failures, and deployment automation.

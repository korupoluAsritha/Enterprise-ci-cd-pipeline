# Enterprise CI/CD Pipeline Project

## Overview

This project is a hands-on DevOps learning repository created to understand how modern enterprise software is built, tested, containerized, and deployed.

The objective is not only to learn individual tools but to understand:

- System architecture
- CI/CD principles
- Root Cause Analysis (RCA)
- Troubleshooting methodology
- Deployment strategies
- Software delivery lifecycle

The repository starts with a Flask application and evolves into a fully automated CI/CD platform.

---

# Current Architecture

```text
Developer
    |
    v
GitHub
    |
    v
Jenkins
    |
    +--> Environment Validation
    |
    +--> Source Code Checkout
    |
    +--> Dependency Installation
    |
    +--> Unit Testing
    |
    +--> Docker Image Build
    |
    +--> Container Deployment
    |
    +--> Health Check
    |
    v
Running Application
```

---

# Technologies Used

## Source Control

- Git
- GitHub

## Application

- Python
- Flask

## Testing

- Pytest

## Containerization

- Docker
- Docker Desktop

## CI/CD

- Jenkins

---

# Current Build Flow

## Step 1: Environment Verification

Jenkins validates:

```cmd
git --version
python --version
docker --version
```

Purpose:

- Verify tools are available
- Detect environment issues early
- Prevent unnecessary build execution

---

## Step 2: Clone Repository

```cmd
git clone
```

Purpose:

- Download latest source code
- Create build workspace

Workspace Example:

```text
C:\ProgramData\Jenkins\.jenkins\workspace\enterprise-cicd-freestyle
```

---

## Step 3: Dependency Installation

```cmd
python -m pip install -r requirements.txt
```

Purpose:

- Install Flask
- Install Pytest
- Prepare application runtime

---

## Step 4: Unit Testing

```cmd
python -m pytest -v
```

Purpose:

- Validate application behavior
- Stop deployments when tests fail

Example:

```text
1 passed
```

---

## Step 5: Docker Build

```cmd
docker build -t flask-app:%BUILD_NUMBER% -t flask-app:latest .
```

Purpose:

- Produce deployable artifact
- Enable rollback using versioned tags

Example:

```text
flask-app:9
flask-app:latest
```

---

## Step 6: Deployment

Deployment strategy:

```text
Stop old container
Remove old container
Run new container
```

Commands:

```cmd
docker stop flask-app
docker rm flask-app

docker run -d --name flask-app -p 5000:5000 flask-app:%BUILD_NUMBER%
```

---

## Step 7: Health Check

```cmd
curl http://localhost:5000
```

Purpose:

Verify that:

```text
Build Success
Deployment Success
Application Success
```

instead of only validating image creation.

---

# CI Principles Applied

## Fail Fast

Tests run before Docker build.

Why?

```text
Bad Code
    |
Tests Fail
    |
Build Stops
```

instead of:

```text
Bad Code
    |
Docker Build
    |
Deployment
    |
Failure
```

---

## Immutable Artifacts

Every build creates:

```text
flask-app:6
flask-app:7
flask-app:8
flask-app:9
```

Benefits:

- Traceability
- Rollback
- Auditability

---

# Future Roadmap

## Pipeline as Code

Convert Freestyle Job into:

```text
Jenkins Pipeline
Jenkinsfile
```

---

## GitHub Automation

```text
git push
    |
GitHub Webhook
    |
Automatic Jenkins Build
```

---

## Application Expansion

Current:

```text
/
```

Planned:

```text
/health
/users
/products
/orders
```

---

## Database

PostgreSQL

Architecture:

```text
Flask
   |
SQLAlchemy
   |
PostgreSQL
```

---

## Kubernetes

Future Architecture:

```text
GitHub
   |
Jenkins
   |
Docker Hub
   |
Kubernetes
```

---

## Observability

Planned:

- Prometheus
- Grafana

---

## Performance Testing

Planned:

- JMeter
- k6

---

# Key Learning

The project focuses on understanding:

```text
Why systems work
Why systems fail
How to troubleshoot
```

rather than simply memorizing commands.

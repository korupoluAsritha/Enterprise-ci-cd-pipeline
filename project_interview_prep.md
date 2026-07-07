# Enterprise CI/CD Project Interview Preparation

---

# Project Summary

Built an automated CI pipeline using:

- GitHub
- Jenkins
- Python
- Flask
- Pytest
- Docker

Pipeline performs:

- Source code retrieval
- Dependency installation
- Unit testing
- Docker image creation

---

# Architecture

```text
Developer
    |
GitHub
    |
Jenkins
    |
Git Clone
    |
Dependency Installation
    |
Pytest
    |
Docker Build
```

---

# Explain Workspace

A Jenkins workspace is a directory where Jenkins stores source code and executes build steps.

Example:

```text
C:\ProgramData\Jenkins\.jenkins\workspace
```

---

# Explain Docker Image

Image:

Immutable template.

Example:

```bash
docker build -t flask-app:v1 .
```

---

# Explain Container

Container:

Running instance of image.

Example:

```bash
docker run -d -p 5000:5000 flask-app:v1
```

---

# Explain Dockerfile

### FROM

Base image.

### WORKDIR

Set working directory.

### COPY

Transfer files.

### RUN

Execute build-time commands.

### EXPOSE

Document application port.

### CMD

Container startup command.

---

# Explain CI

Continuous Integration means:

Developers continuously merge code.

Automated systems:

- Build
- Test
- Validate

changes immediately.

---

# Explain Why Tests Run Before Docker Build

Benefits:

- Fail Fast
- Reduced resource consumption
- Faster feedback

---

# Explain BUILD_NUMBER

Jenkins automatically generates:

```text
1
2
3
4
```

These can be used for image tagging.

Example:

```text
flask-app:6
```

---

# Jenkins Interview Questions

## What is Jenkins?

Automation server used for CI/CD.

---

## What is a Workspace?

Location where builds execute.

---

## What is a Freestyle Job?

UI-configured Jenkins job.

---

## What is a Pipeline Job?

Code-based CI/CD workflow defined using Jenkinsfile.

---

## Why Use Pipelines?

Advantages:

- Version control
- Repeatability
- Scalability
- Reviewability

---

# Docker Interview Questions

## Difference Between Image and Container

Image:

Blueprint.

Container:

Running instance.

---

## What Happens During Docker Build?

Docker executes instructions in Dockerfile and creates image layers.

---

## Why Use Docker?

Benefits:

- Portability
- Consistency
- Isolation

---

# Git Interview Questions

## Difference Between Git and GitHub

Git:

Version control tool.

GitHub:

Remote repository platform.

---

## What Is a Remote?

Remote repository associated with local repository.

Example:

```bash
git remote -v
```

---

# Real RCA Example

Problem:

```text
pytest not recognized
```

Investigation:

Confirmed Python available.

Confirmed pytest installed.

Finding:

PATH issue.

Fix:

```cmd
python -m pytest
```

Learning:

Understand systems, not just commands.

---

# Future Enterprise Architecture

```text
GitHub
   |
Webhook
   |
Jenkins Pipeline
   |
Unit Tests
   |
SonarQube
   |
Trivy
   |
Docker Build
   |
DockerHub
   |
Kubernetes
   |
Prometheus
   |
Grafana
```

---

# Resume Summary

Built an enterprise-style CI pipeline using Jenkins, GitHub, Flask, Docker, and Pytest. Automated source code retrieval, dependency installation, testing, and container image creation while troubleshooting Git, Docker, and Jenkins integration issues using a root-cause-analysis approach.

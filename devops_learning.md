# DevOps Learning Journal

# Core Philosophy

A DevOps Engineer should understand:

```text
Architecture
Automation
Troubleshooting
Root Cause Analysis
```

not just tool commands.

---

# Git Learnings

## What is Git?

Distributed version control system.

Purpose:

- Track changes
- Maintain history
- Enable collaboration

---

## Important Concepts

### Repository

Collection of files and commits.

### Commit

Snapshot of changes.

### Branch

Independent line of development.

### Remote

External repository.

Example:

```bash
git remote -v
```

---

## Learning

Git push failures are usually:

```text
History conflicts
Authentication issues
Branch protection
```

not Git failures.

---

# Docker Learnings

## Docker Architecture

```text
Docker CLI
       |
       v
Docker Daemon
       |
       v
Images
       |
       v
Containers
```

---

## Image

Immutable application template.

Example:

```bash
docker build -t flask-app:v1 .
```

---

## Container

Running process created from image.

Example:

```bash
docker run flask-app:v1
```

---

## Important Learning

Image:

```text
Static
```

Container:

```text
Running
```

---

# Jenkins Learnings

## Jenkins Architecture

```text
Jenkins Controller
         |
         +--> Jobs
         |
         +--> Workspaces
         |
         +--> Build History
```

---

## Workspace

Purpose:

Temporary build location.

Example:

```text
C:\ProgramData\Jenkins\.jenkins\workspace
```

---

## Build Lifecycle

```text
Build Trigger
      |
Workspace Creation
      |
Source Checkout
      |
Testing
      |
Artifact Build
      |
Deployment
```

---

# CI/CD Learnings

## Continuous Integration

Purpose:

Verify every code change quickly.

Activities:

```text
Build
Test
Validate
```

---

## Continuous Delivery

Purpose:

Deploy validated code automatically.

Activities:

```text
Docker Build
Deployment
Health Check
```

---

# Deployment Learnings

Current Strategy:

```text
Stop
Remove
Deploy
```

Flow:

```text
Current Container
      |
Stop
      |
Remove
      |
Deploy New Version
```

---

# Health Checks

Build success does not guarantee:

```text
Application Success
```

Need:

```text
Health Verification
```

Example:

```bash
curl http://localhost:5000
```

---

# Build Numbers

Jenkins automatically generates:

```text
1
2
3
4
...
```

Used for:

```text
Docker Image Versioning
```

Example:

```text
flask-app:9
```

---

# Root Cause Analysis Framework

Always ask:

1. What failed?
2. Where did it fail?
3. What evidence proves it?
4. What caused it?
5. What fixed it?
6. How can recurrence be prevented?

---

# Future Learning Areas

- Jenkins Pipelines
- GitHub Webhooks
- PostgreSQL
- Docker Compose
- Docker Hub
- Kubernetes
- Prometheus
- Grafana
- Trivy
- SonarQube
- Load Testing

---

# Most Valuable Lesson

Learning through troubleshooting creates deeper understanding than learning through tutorials alone.

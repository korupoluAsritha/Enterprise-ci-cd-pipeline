# Enterprise CI/CD Pipeline

## Project Overview

This project is an evolving enterprise-grade DevOps portfolio project built to simulate real-world software delivery workflows.

The goal is not just to deploy a Flask application but to understand:

- Git and GitHub workflows
- CI/CD pipelines
- Docker containerization
- Jenkins automation
- Root Cause Analysis (RCA)
- DevOps troubleshooting
- Enterprise software delivery practices

---

# Current Architecture

```text
Developer
    |
    v
GitHub Repository
    |
    v
Jenkins Freestyle Job
    |
    +--> Environment Validation
    |
    +--> Git Clone
    |
    +--> Install Dependencies
    |
    +--> Execute Tests
    |
    +--> Build Docker Image

Technologies Used
Source Control

Git
GitHub

Application

Python
Flask

Testing

Pytest

Containerization

Docker
Docker Desktop

CI

Jenkins


Repository Structure
Plain Text.├── app.py├── test_home.py├── requirements.txt├── Dockerfile├── Jenkinsfile├── README.md├── devops_learning.md├── troubleshooting_guide.md└── project_interview_prep.mdShow more lines

Current CI Workflow
Environment Validation
BATgit --versionpython --versiondocker --versionShow more lines
Purpose:

Verify Jenkins can access required tools.


Source Code Checkout
BATgit cloneShow more lines
Purpose:

Pull application code into Jenkins workspace.


Dependency Installation
BATpython -m pip install -r requirements.txtShow more lines
Purpose:

Install Flask
Install Pytest


Test Execution
BATpython -m pytest -vShow more lines
Purpose:

Validate application behavior before creating Docker image.


Docker Build
BATdocker build -t flask-app:%BUILD_NUMBER% .Show more lines
Purpose:

Build versioned Docker image.

Examples:
Plain Textflask-app:1flask-app:2flask-app:3Show more lines

Major Learnings
This project focused heavily on understanding:

Why things fail
How tools communicate
How to debug systems
How CI/CD works internally

Instead of only learning commands.

Future Roadmap
Jenkins

Install Pipeline Plugin
Install Git Plugin
Convert Freestyle Job to Jenkinsfile Pipeline

GitHub

Configure Webhooks
Automatic Builds

Security

Trivy
SonarQube
pip-audit

Application
Convert Flask app into:
Plain TextFrontendBackendDatabaseShow more lines
using:

Flask
PostgreSQL
SQLAlchemy

CD
Deploy to:

Docker Hub
Kubernetes

Monitoring

Prometheus
Grafana

Load Testing

JMeter
k6


End Goal
Plain TextGitHub   |Webhook   |Jenkins Pipeline   |Unit Tests   |Security Scans   |Docker Build   |DockerHub   |Kubernetes   |Prometheus   |GrafanaShow more lines
A complete enterprise-style DevOps platform.

---

# devops_learning.md

````md
# DevOps Learning Journal

---

# Objective

Become a job-ready DevOps Engineer by building an enterprise-style CI/CD platform from scratch while understanding:

- Architecture
- Tool internals
- Troubleshooting
- RCA
- Deployment workflows

---

# Learning Philosophy

Do not memorize commands.

Understand:

```text
How it works
Why it fails
How to troubleshoot

This project follows:
Plain TextBuildBreakFixDocumentRepeatShow more lines

Git Learnings
Git Remote
Check remote:
Shellgit remote -vShow more lines
Purpose:

Identify remote repository mappings.


Git Push Failure
Error:
Plain Textnon-fast-forwardShow more lines
Meaning:
Remote repository already had commits.
Learning:
Git maintains commit history consistency.

Git Concepts
Repository
Plain TextCollection of source code and commits.Show more lines
Commit
Plain TextImmutable snapshot.Show more lines
Branch
Plain TextIndependent line of development.Show more lines
Remote
Plain TextRepository stored on GitHub.Show more lines

Docker Learnings
Docker Architecture
Plain TextDocker CLI     |     vDocker Daemon     |     vImages     |     vContainersShow more lines
Important:
Installing Docker CLI does not mean Docker Engine is running.

Image
Blueprint.
Example:
Shelldocker build -t flask-app:v1 .Show more lines

Container
Running instance of image.
Example:
Shelldocker run -d -p 5000:5000 flask-app:v1Show more lines

Dockerfile
Purpose:
Build application image.
Components:
FROM
Base image
WORKDIR
Working directory
COPY
Copy files
RUN
Execute commands during build
EXPOSE
Document listening port
CMD
Container startup command

Jenkins Learnings
Jenkins Architecture
Plain TextJenkins Controller         |         +--> Workspace         |         +--> Build StepsShow more lines

Workspace
Example:
Plain TextC:\ProgramData\Jenkins\.jenkins\workspaceShow more lines
Purpose:
Temporary build location.

Freestyle Job
UI-driven.
Configured through Jenkins interface.

Pipeline Job
Code-driven.
Defined using:
Plain TextJenkinsfileShow more lines
Not yet implemented because plugin ecosystem is currently broken.

Build Flow
Plain TextBuild Trigger      |Workspace Creation      |Git Clone      |Install Dependencies      |Run Tests      |Build Docker Image      |Store LogsShow more lines

Enterprise CI/CD Concepts
Fail Fast
Order:
Plain TextTests   |Docker BuildShow more lines
not
Plain TextDocker Build   |TestsShow more lines
Reason:
Avoid wasting resources.

Versioned Images
Bad:
Plain TextlatestShow more lines
Good:
Plain Textflask-app:6Show more lines
Benefits:

Rollback
Traceability
Auditing


Future Learning Areas
Webhooks
Plain TextGit Push    |GitHub Webhook    |Jenkins BuildShow more lines

DevSecOps

Trivy
SonarQube
pip-audit


Kubernetes

Deployments
Services
Ingress
HPA


Monitoring

Prometheus
Grafana


Load Testing

k6
JMeter


Root Cause Analysis
Always ask:

What failed?
Where did it fail?
What evidence proves it?
What caused it?
How do we fix it?
How can we prevent recurrence?

This mindset separates engineers from tool users.

---

# troubleshooting_guide.md

````md
# Troubleshooting Guide

---

# Issue 1

## Docker Build Failed

Error:

```text
docker buildx build requires 1 argument
```

Cause:

Build context missing.

Wrong:

```bash
docker build -t flask-app:v1
```

Correct:

```bash
docker build -t flask-app:v1 .
```

Learning:

The dot represents the build context.

---

# Issue 2

## Docker Daemon Not Running

Error:

```text
failed to connect to dockerDesktopLinuxEngine
```

Cause:

Docker Desktop not running.

Diagnosis:

```bash
docker info
```

Learning:

CLI and Engine are different components.

---

# Issue 3

## Dockerfile Missing

Error:

```text
failed to read dockerfile
```

Cause:

Dockerfile not found.

Verification:

```bash
ls
```

Fix:

Ensure filename:

```text
Dockerfile
```

not

```text
DockerFile
```

---

# Issue 4

## Slow Docker Build

Observation:

9MB context transfer took several minutes.

Root Cause:

Large files included in build context.

Fix:

Create:

```text
.dockerignore
```

Contents:

```text
.venv
.git
__pycache__
```

Learning:

Docker uploads entire build context.

---

# Issue 5

## Git Push Rejected

Error:

```text
non-fast-forward
```

Cause:

Repository histories differ.

Fix:

```bash
git pull
```

or

```bash
git push --force
```

after validation.

---

# Issue 6

## Jenkins Pipeline Option Missing

Observation:

Only Freestyle Job available.

Investigation:

Checked installed plugins.

Finding:

Pipeline plugins not installed.

Root Cause:

Broken plugin dependency chain.

---

# Issue 7

## Jenkins Plugin Installation Failure

Error:

```text
SocketTimeoutException
```

Investigation:

Verified:

```text
Browser access ✅
Jenkins URL access ✅
```

Finding:

Plugin dependencies missing.

Examples:

```text
workflow-step-api
workflow-support
display-url-api
```

Learning:

Network symptom was not the root cause.

Dependency chain failure was the root cause.

---

# Issue 8

## Execute Shell Failed

Error:

```text
Cannot run program "sh"
```

Cause:

Used:

```text
Execute Shell
```

on Windows.

Fix:

Use:

```text
Execute Windows batch command
```

---

# Issue 9

## Pytest Not Found

Error:

```text
pytest is not recognized
```

Cause:

PATH issue.

Fix:

```cmd
python -m pytest
```

Learning:

Module invocation is more reliable than executable invocation.

---

# Successful CI Flow

```text
Environment Check ✅

Git Clone ✅

Dependency Installation ✅

Pytest ✅

Docker Build ✅
```

---

# Troubleshooting Framework

Always follow:

## Symptom

What failed?

## Evidence

What logs prove it?

## Root Cause

Why did it happen?

## Fix

How was it corrected?

## Prevention

How can we stop recurrence?

Following this framework dramatically improves debugging effectiveness.



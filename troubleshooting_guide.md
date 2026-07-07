# Troubleshooting Guide

---

# Issue 1

## Docker Build Failed

Error:

```text
docker buildx build requires 1 argument
```

Cause:

Missing build context.

Wrong:

```bash
docker build -t flask-app:v1
```

Correct:

```bash
docker build -t flask-app:v1 .
```

Learning:

Docker needs a build context.

The dot (.) means current directory.

---

# Issue 2

## Docker Daemon Not Running

Error:

```text
failed to connect to dockerDesktopLinuxEngine
```

Cause:

Docker Desktop not running.

Investigation:

```bash
docker info
```

Fix:

Start Docker Desktop.

Learning:

Docker CLI != Docker Engine

Architecture:

CLI
|
v
Docker Daemon
|
v
Containers

---

# Issue 3

## Dockerfile Missing

Error:

```text
failed to read dockerfile
```

Cause:

Dockerfile missing or incorrectly named.

Investigation:

```bash
ls -la
```

Fix:

Rename:

```text
DockerFile
```

to:

```text
Dockerfile
```

Learning:

Linux containers are case-sensitive.

---

# Issue 4

## Slow Docker Build

Symptom:

9 MB context took 580+ seconds.

Cause:

Files being unnecessarily copied.

Likely:

```text
.venv
.git
```

Fix:

Create .dockerignore

```text
.venv
.git
__pycache__
.pytest_cache
```

Learning:

Docker uploads the entire build context.

---

# Issue 5

## Git Push Rejected

Error:

```text
non-fast-forward
```

Cause:

Remote repository already contained commits.

Investigation:

```bash
git fetch origin
git log
```

Fix:

```bash
git pull --allow-unrelated-histories
```

or

```bash
git push --force
```

Learning:

Local and remote commit histories must align.

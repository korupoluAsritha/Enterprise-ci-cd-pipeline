# DevOps Learning Journal

## Project

Enterprise CI/CD Pipeline

## Goal

Build a production-style CI/CD pipeline using:

- Git
- GitHub
- Flask
- Docker
- Jenkins

Architecture:

Developer
|
v
GitHub
|
v
Jenkins
|
+--> Build
+--> Test
+--> Docker Build
+--> Deploy

---

# Skills Learned

## Git

### Commands

```bash
git init
git add .
git commit -m "message"
git push origin main
git pull origin main
git fetch origin
git remote -v
```

### Concepts

- Repository
- Commit
- Branch
- Remote
- Origin

---

## Docker

### Commands

```bash
docker build -t image .
docker images
docker run -d -p 5000:5000 image
docker ps
docker logs container
docker exec -it container sh
```

### Concepts

Image

Blueprint for container.

Container

Running instance of image.

Dockerfile

Instructions used to build image.

---

## Jenkins

### Freestyle Job

UI driven.

### Pipeline Job

Code driven.

### Jenkinsfile

Stores pipeline definition.

```
GitHub
|
v
Jenkins Pipeline
|
v
Build Stages
```

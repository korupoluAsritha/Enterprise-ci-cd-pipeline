# Enterprise CI/CD Pipeline Interview Notes

## Explain Dockerfile

```dockerfile
FROM python:3.13-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python", "app.py"]
```

### FROM

Base image containing Python.

### WORKDIR

Creates and switches to /app.

### COPY

Copies files into image.

### RUN

Executes during image build.

### EXPOSE

Documents application port.

### CMD

Runs application when container starts.

---

# Explain Docker Image vs Container

Image:

Blueprint.

Container:

Running instance of image.

Example:

```text
Image
 |
 +--> Container1
 +--> Container2
 +--> Container3
```

---

# Explain Jenkins Pipeline

Stages:

1. Checkout
2. Install Dependencies
3. Run Tests
4. Build Docker Image
5. Deploy

Purpose:

Automate software delivery.

---

# Explain Today's Architecture

Developer
|
v
GitHub
|
v
Jenkins
|
v
Docker Build
|
v
Container

---

# Common Interview Question

Q: How did you verify Jenkins can communicate with Docker?

A:

Created a Freestyle Job and executed:

```cmd
docker version
```

Successful client and server output confirmed Jenkins-Docker connectivity.

---

# Common RCA Question

Q: Docker build failed. How do you troubleshoot?

1. Read error carefully.
2. Identify failing layer.
3. Validate Docker daemon.
4. Check Dockerfile.
5. Check build context.
6. Review logs.

Commands:

```bash
docker info
docker images
docker ps
docker logs
docker build .
```

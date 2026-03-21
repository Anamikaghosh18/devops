# Containerization Guide (Docker)

## Introduction

Containerization is a technique used to package an application along with its dependencies, libraries, and configuration files into a **container** so that it runs consistently across different environments.

A container ensures that the application behaves the same on a developer’s machine, testing server, and production environment.

Common tools used for containerization:

* Docker
* Kubernetes

---

# Why Containerization?

### Problems Without Containers

* “It works on my machine” problem
* Dependency conflicts
* Different environments for development and production
* Difficult deployments

### Benefits

* Environment consistency
* Lightweight compared to Virtual Machines
* Faster deployment
* Easy scalability
* Isolation between applications

---

# Containers vs Virtual Machines

| Feature      | Containers           | Virtual Machines       |
| ------------ | -------------------- | ---------------------- |
| OS           | Share host OS kernel | Each VM has its own OS |
| Startup Time | Seconds              | Minutes                |
| Size         | Lightweight (MBs)    | Heavy (GBs)            |
| Performance  | Near-native          | Slightly slower        |

---

# Docker Architecture

Docker consists of the following components:

1. **Docker Client**

   * Command line interface used to run Docker commands.

2. **Docker Daemon**

   * Background service that builds, runs, and manages containers.

3. **Docker Images**

   * Read-only templates used to create containers.

4. **Docker Containers**

   * Running instances of Docker images.

---

# Basic Docker Commands

### Check Docker Version

```bash
docker --version
```

### Check Docker Info

```bash
docker info
```

### List Running Containers

```bash
docker ps
```

### List All Containers

```bash
docker ps -a
```

### List Images

```bash
docker images
```

---

# Running Your First Container

```bash
docker run hello-world
```

This command downloads the **hello-world image** and runs it in a container.

---

# Pulling an Image from Docker Hub

```bash
docker pull node
```

---

# Running a Container

```bash
docker run -d -p 3000:3000 node
```

Explanation:

* `-d` → run container in background
* `-p` → map port (host:container)

---

# Stopping a Container

```bash
docker stop <container_id>
```

---

# Removing a Container

```bash
docker rm <container_id>
```

---

# Removing an Image

```bash
docker rmi <image_id>
```

---

# Creating a Dockerfile

A **Dockerfile** contains instructions to build a Docker image.

Example:

```Dockerfile
FROM node:18

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
```

---

# Build Docker Image

```bash
docker build -t my-app .
```

Explanation:

* `-t` → tag the image
* `.` → current directory

---

# Run Container from Image

```bash
docker run -p 3000:3000 my-app
```

---

# Docker Compose

Docker Compose is used to run **multiple containers together**.

Example `docker-compose.yml`:

```yaml
version: "3"

services:
  app:
    build: .
    ports:
      - "3000:3000"

  database:
    image: mongo
    ports:
      - "27017:27017"
```

Run containers:

```bash
docker-compose up
```

Stop containers:

```bash
docker-compose down
```

---

# Container Lifecycle

1. Create container
2. Start container
3. Run container
4. Stop container
5. Remove container

---

# Best Practices

* Use **small base images**
* Avoid running containers as root
* Use `.dockerignore`
* Keep containers stateless
* Use environment variables for configuration

---

# Example Workflow

1. Write application code
2. Create Dockerfile
3. Build Docker image

```bash
docker build -t my-app .
```

4. Run container

```bash
docker run -p 3000:3000 my-app
```

5. Deploy container to server or cloud

---

# Summary

Containerization allows developers to package applications and dependencies into isolated containers, ensuring consistency across environments and simplifying deployment.

Docker is the most widely used containerization platform, while Kubernetes is commonly used to manage and scale containers in production.

---

# Useful Commands Cheat Sheet

```bash
docker build -t image_name .
docker run -p 3000:3000 image_name
docker ps
docker ps -a
docker images
docker stop container_id
docker rm container_id
docker rmi image_id
docker-compose up
docker-compose down
```

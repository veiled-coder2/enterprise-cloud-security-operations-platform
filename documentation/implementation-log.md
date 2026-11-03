# 📝 Implementation Log

## Project: Enterprise Cloud Security Operations Platform

**Date:** November 3, 2026

**Phase:** 1 – Local Application Deployment

**Focus:** OWASP Juice Shop, Docker Fundamentals and GitHub Repository Setup

---

## 🎯 Objectives

The objectives for this session were to:

- Set up OWASP Juice Shop as the application's initial testing workload.
- Understand how Docker images and containers work.
- Download the Juice Shop Docker image.
- Deploy the application locally using Docker.
- Explore basic Docker container management commands.
- Create and initialise the project's GitHub repository.
- Document the initial implementation.

## 🐳 1. Docker Image Acquisition

The first task was to obtain the OWASP Juice Shop image from Docker Hub.

**Command:**

```bash
docker pull bkimminich/juice-shop
```

### Challenge Encountered

The initial attempt to download the image failed due to a DNS/network resolution error when Docker Desktop attempted to reach Docker Hub's authentication server (`auth.docker.io`).

The error indicated that Docker Desktop could not resolve the hostname.

### Troubleshooting

The following commands were used to investigate the issue:

**DNS resolution test:**

```bash
nslookup auth.docker.io
```

The hostname successfully resolved to IP addresses.

**HTTPS connectivity test:**

```powershell
Test-NetConnection auth.docker.io -Port 443
```

The result was:

```text
TcpTestSucceeded : True
```

This confirmed that the Windows host could establish an HTTPS connection to Docker Hub's authentication server.

The issue was subsequently resolved, and the Docker image was successfully downloaded.

## 🐳 2. Container Deployment

After downloading the image, the next step was to create and start a container.

**Command:**

```bash
docker run -d -p 3000:3000 --name juice-shop bkimminich/juice-shop
```

### Understanding the Command

| Option | Purpose |
|---|---|
| `docker run` | Creates and starts a container from an image. |
| `-d` | Runs the container in detached mode (background). |
| `-p 3000:3000` | Maps host port 3000 to container port 3000. |
| `--name juice-shop` | Assigns the container the name `juice-shop`. |
| `bkimminich/juice-shop` | Specifies the Docker image used to create the container. |

The application is accessed locally through:

```text
http://localhost:3000
```

## 🔍 3. Container Inspection and Management

The following Docker commands were explored:

| Command | Purpose |
|---|---|
| `docker ps` | Displays currently running containers. |
| `docker ps -a` | Displays all containers, including stopped containers. |
| `docker logs juice-shop` | Displays the container's application logs. |
| `docker inspect juice-shop` | Displays detailed container configuration and metadata. |
| `docker stop juice-shop` | Stops the running container. |
| `docker start juice-shop` | Starts an existing stopped container. |

### Key Concepts Learned

**Docker Image vs Container**

- An image is a packaged template containing the application and its required dependencies.
- A container is a running or stopped instance created from an image.

**Container Lifecycle**

Stopping a container does not delete it. The container remains available and can be restarted using `docker start`.

**Container Listing**

- `docker ps` displays running containers.
- `docker ps -a` displays all existing containers, including stopped and exited containers.

**Port Mapping**

The `-p 3000:3000` option maps port 3000 on the host machine to port 3000 inside the container, allowing the application to be accessed through the host's localhost address.

## 🗂️ 4. GitHub Repository Setup

A GitHub repository was created to maintain the project's source files, documentation, implementation records and future infrastructure configurations.

**Repository:**

`enterprise-cloud-security-operations-platform`

**Branch:** `master`

The initial README was created to document:

- Project overview and objectives.
- Technology stack.
- Current implementation.
- Local deployment instructions.
- Planned implementation roadmap.
- Security considerations.

The local project was connected to GitHub using a remote named `origin`, and the initial project files were pushed to the remote repository.

## 📚 5. Key Takeaways

By the end of this session, I gained practical experience with:

1. Obtaining container images from Docker Hub.
2. Understanding the relationship between Docker images and containers.
3. Creating and running containers.
4. Mapping host and container ports.
5. Inspecting container status and configuration.
6. Understanding the difference between running and stopped containers.
7. Managing the basic container lifecycle.
8. Troubleshooting Docker Hub connectivity issues.
9. Initialising a Git repository and connecting it to a GitHub remote.
10. Maintaining project documentation using Markdown.

## ⏭️ 6. Next Steps

The next implementation activities will focus on:

- Exploring Docker image management.
- Understanding container networking in more detail.
- Learning container removal and image removal.
- Deepening understanding of Docker container configuration.
- Preparing for local Kubernetes deployment using Kind.

---

**Status:** 🚧 Phase 1 – In Progress
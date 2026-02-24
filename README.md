# Project Overview

This project demonstrates the containerization and deployment of a
full-stack MEAN (MongoDB, Express, Angular, Node.js) application using
Docker, Docker Compose, GitHub Actions CI/CD, and Nginx reverse proxy on
an AWS Ubuntu VM.

# Tech Stack

-   MongoDB
-   Express.js
-   Angular
-   Node.js
-   Docker
-   Docker Compose
-   GitHub Actions (CI/CD)
-   Nginx (Reverse Proxy)
-   Ubuntu VM (AWS Deployment)

# Steps

# Repository Setup

1.  Created a new GitHub repository.
2.  Added backend and frontend source code.
3.  Added:
    -   Dockerfile /backend
    -   Dockerfile /frontend
    -   docker-compose.yml
    -   .github/workflows/deploy.yml

# Dockerization

# Backend Dockerfile

-   Uses Node base image
-   Installs dependencies
-   Exposes port 3000
-   Runs server.js

# Frontend Dockerfile

-   Builds Angular app
-   Uses Nginx to serve static files
-   Exposes port 80

# Docker Compose

Services: - mongo (Official MongoDB image) - backend (DockerHub image) -
frontend (DockerHub image)

Command used on VM:

    docker-compose up -d

# GitHub Actions

Pipeline Triggers: - Push to master branch

Pipeline Steps: 1. Checkout code 2. Login to DockerHub using access
token 3. Build backend image 4. Push backend image 5. Build frontend
image 6. Push frontend image 7. SSH into VM 8. Pull latest images 9.
Restart containers

# Nginx Reverse Proxy 

-   Used nginx image inside frontend
-   Configured to listen on port 80
-   Proxies requests to frontend container
-   Backend communicates internally via Docker network

# Deployment

User → Nginx (Port 80) → Frontend Container → Backend Container →
MongoDB Container

# Screenshots

Add the following screenshots in a folder named `screenshots/`:

1.  CI/CD Pipeline Execution (GitHub Actions)
2.  Docker Image Build & Push Logs
3.  Running Containers on VM (`docker ps`)
4.  Working Application UI in Browser
5.  Nginx Configuration File

3.  Add inside README like this:

```{=html}
<!-- -->
```
    ![CI/CD Success](screenshots/cicd-success.png)
    ![Docker Build](screenshots/docker-build.png)
    ![Application UI](screenshots/app-ui.png)





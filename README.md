# Project Overview

This project demonstrates the containerization and deployment of a
full-stack MEAN (MongoDB, Express, Angular, Node.js) application using
Docker, Docker Compose, GitHub Actions CI/CD, and Nginx reverse proxy on
an AWS Ubuntu VM.

Deployed Public IP: 13.127.152.253

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
1.  CI/CD Pipeline Execution (GitHub Actions)
   ![image alt](https://github.com/NakulNijampurkar/crud-dd/blob/1b01706da25347a9d3e9da9c0ede42f243ce32df/pipline.png)
3.  Docker Image Build & Push Logs
   ![image alt](https://github.com/NakulNijampurkar/crud-dd/blob/1b01706da25347a9d3e9da9c0ede42f243ce32df/logs.png)
5.  Running Containers on VM 
   ![image alt](https://github.com/NakulNijampurkar/crud-dd/blob/1b01706da25347a9d3e9da9c0ede42f243ce32df/docker%20ps%20on%20vm.png)
7.  Working Application UI in Browser
   ![image alt](https://github.com/NakulNijampurkar/crud-dd/blob/1b01706da25347a9d3e9da9c0ede42f243ce32df/dd%20task%201.png)
8.  Nginx Configuration File
   ![image alt](https://github.com/NakulNijampurkar/crud-dd/blob/1b01706da25347a9d3e9da9c0ede42f243ce32df/nginx%20conf.png)





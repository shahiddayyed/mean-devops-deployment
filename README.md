Assigement Overview

This project demonstrates containerization and automated deployment of a full-stack MEAN application using:

MongoDB

Express.js

Angular 15

Node.js

Docker & Docker Compose

AWS EC2 (Ubuntu 22.04)

Nginx Reverse Proxy

GitHub Actions CI/CD
-------------------------------------------
Architecture ;-

Developer Push → GitHub
        ↓
GitHub Actions
        ↓
Build Docker Images
        ↓
Push to Docker Hub
        ↓
SSH to EC2
        ↓
docker compose pull
        ↓
Containers Restart
        ↓
Live Application Updated
-------------------------------------------
Production Infrastructure:-

Internet
   ↓
EC2 (Port 80)
   ↓
Nginx (Reverse Proxy)
   ↓
Frontend Container (Angular)
   ↓
Backend Container (Node/Express)
   ↓
MongoDB Container (Persistent Volume)
-------------------------------------------
Containerization :-

Backend

Node 18 Alpine base image

Environment variable based MongoDB connection

Exposes port 8080

Frontend

Multi-stage Docker build

Angular production build

Served via Nginx

MongoDB

Official mongo:latest image

Persistent Docker volume
-------------------------------------------
AWS Deployment :-

Ubuntu 22.04 EC2 instance

Docker installed using official Docker repository

Images pulled from Docker Hub

Deployed using docker-compose.yml
-------------------------------------------
Application URL: http://13.233.106.26/
-------------------------------------------
CI/CD Pipeline

Implemented using GitHub Actions.

On every push to main:

Build backend Docker image

Build frontend Docker image

Push images to Docker Hub

SSH into EC2

Pull latest images

Restart containers

Remove unused images

Workflow file:

.github/workflows/deploy.yml
-------------------------------------------
Security Considerations

Docker Hub credentials stored in GitHub Secrets

SSH private key stored securely in GitHub Secrets

No sensitive data committed to repository
-------------------------------------------
Key Learnings

Multi-stage Docker builds

Reverse proxy configuration

Docker networking

Persistent volumes

CI/CD automation

Image-based production deployment

Secure secret management
-------------------------------
<img width="1053" height="259" alt="Screenshot 2026-02-24 at 4 41 38 PM" src="https://github.com/user-attachments/assets/9456d0ff-fa43-4663-bd85-c1531c39c1c6" />






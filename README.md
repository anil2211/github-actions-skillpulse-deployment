🚀 SkillPulse – CI/CD Deployment with GitHub Actions
📌 Project Overview

This project demonstrates a complete CI/CD pipeline for a 3-tier application using GitHub Actions, Docker, and AWS EC2.
The application is automatically built, pushed, and deployed on an EC2 instance using a fully automated pipeline.

It simulates a real-world DevOps production deployment workflow.

🏗️ Architecture
Frontend → Nginx (Docker Container)
Backend → API service (Go/Gin or Node.js container)
Database → MySQL (Docker Container)
CI/CD Tool → GitHub Actions
Deployment Server → AWS EC2 (Ubuntu)
Containerization → Docker + Docker Compose
⚙️ Tech Stack
Git & GitHub
GitHub Actions (CI/CD)
Docker & Docker Compose
AWS EC2 (Ubuntu)
Nginx (Frontend hosting)
MySQL (Database)
📂 Project Structure
github-actions-skillpulse-deployment/
│
├── .github/
│   └── workflows/
│       └── ci.yml        # CI pipeline
│       └── cd.yml        # CD pipeline
│
├── docker-compose.yml
├── .env                  # Environment variables (on server)
└── README.md
🔄 CI/CD Workflow
1️⃣ CI Pipeline (Continuous Integration)
Code pushed to GitHub
GitHub Actions triggers ci.yml
Builds Docker images
Pushes images to Docker Hub
2️⃣ CD Pipeline (Continuous Deployment)
Triggered after CI success
Connects to EC2 via SSH
Pulls latest code
Runs deployment commands:
docker compose pull
docker compose up -d
docker image prune -f
🛠️ EC2 Setup (Server Configuration)
1. Launch EC2 Instance (Ubuntu)
Instance Type: t2.medium / t2.large
Security Group:
SSH (22)
HTTP (80)
MySQL (3306 - optional)
2. Install Dependencies
sudo apt-get update -y
sudo apt-get install -y docker.io
sudo apt-get install -y docker-compose-v2
3. Enable Docker Access
sudo usermod -aG docker ubuntu
newgrp docker
docker ps
🔐 GitHub Secrets Configuration

Go to:

👉 GitHub Repository → Settings → Secrets and Variables → Actions

Add:

Secret Name	Description
DOCKER_USERNAME	Docker Hub username
DOCKER_PASSWORD	Docker Hub password/token
EC2_HOST	Public IP of EC2
EC2_USER	ubuntu
EC2_SSH_KEY	PEM private key
📦 Docker Setup
docker-compose.yml

Used to run:

Frontend container
Backend container
MySQL database container
🌐 Environment File (.env on EC2)

Create .env file on EC2 server:

DB_HOST=db
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=skillpulse
🚀 Deployment Flow
Developer Push → GitHub → CI Pipeline → Docker Build → Docker Hub
                                         ↓
                                CD Pipeline Trigger
                                         ↓
                              SSH into EC2 Server
                                         ↓
                        docker compose pull & up -d
                                         ↓
                              Application Live 🚀
📸 Result

After successful deployment:

Frontend → http://EC2-PUBLIC-IP
Backend API → http://EC2-PUBLIC-IP:8080
Database → MySQL container running
🎯 Key Learnings
CI/CD automation using GitHub Actions
Docker container orchestration
AWS EC2 deployment workflow
Real-world DevOps pipeline design
Secure secret management
🔥 Future Improvements
Add HTTPS using Nginx + SSL (Let’s Encrypt)
Add Kubernetes deployment
Add monitoring (Prometheus + Grafana)
Add rollback strategy in CD pipeline
👨‍💻 Author

Anil Choudhary
DevOps Engineer | AWS | Docker | Kubernetes | CI/CD

![alt text](image-1.png)
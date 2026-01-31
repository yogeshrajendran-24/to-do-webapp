# CI/CD Pipeline with Jenkins, SonarQube & Docker

This project demonstrates an end-to-end **CI/CD pipeline** that automates code quality checks, containerization, and deployment of a web application using **Jenkins, SonarQube, Docker, and AWS EC2**.

---

## 🚀 Project Overview

The goal of this project is to build a fully automated CI/CD workflow where every code push triggers:
- Build and validation
- Static code analysis
- Docker image creation
- Image push to Docker Hub
- Deployment on AWS EC2

The application is served using **Nginx** and is accessible via the **EC2 public IP on port 80**.

---

## 🛠️ Tech Stack

- **Version Control:** Git, GitHub  
- **CI/CD:** Jenkins, GitHub Webhook  
- **Code Quality:** SonarQube  
- **Containerization:** Docker  
- **Image Registry:** Docker Hub  
- **Cloud:** AWS EC2  
- **OS:** Ubuntu Linux  
- **Web Server:** Nginx  

---

## 🔁 CI/CD Pipeline Flow

1. Developer pushes code to GitHub  
2. GitHub Webhook triggers Jenkins pipeline  
3. Jenkins stages:
   - Checkout source code
   - Run validation tests
   - Perform SonarQube code analysis
   - Build Docker image
   - Push image to Docker Hub
4. Jenkins deploys the latest Docker image on AWS EC2  
5. Application is accessible via EC2 public IP over HTTP  

---

## 🧱 Architecture Diagram (ASCII)


Developer
   |
   | git push
   v
GitHub
   |
   | webhook
   v
Jenkins
   |
   | test + sonar + docker build
   v
DockerHub
   |
   | pull image
   v
EC2 (Docker + Nginx)
   |
   | http : 80
   v
User Browser 


📂 Project Structure

.
├── index.html
├── style.css
├── script.js
├── Dockerfile
├── Jenkinsfile
├── sonar-project.properties
├── test.sh
└── README.md

🧪 Testing
A simple shell-based validation script (test.sh) is used to verify:

Presence of required files

Basic content validation before build and deployment

📊 Code Quality
Static code analysis is performed using SonarQube

Pipeline fails automatically if the Quality Gate conditions are not met

Ensures zero bugs, vulnerabilities, and code smells before deployment

🐳 Docker & Deployment
Application is containerized using Docker

Docker image is pushed to Docker Hub

Jenkins automatically pulls the latest image on EC2

Container is restarted to reflect the latest changes

Nginx serves the static web app over port 80

🌐 Application Access
http://<EC2_PUBLIC_IP>
(No port number required)

✅ Key Outcomes
Fully automated CI/CD pipeline

Improved code quality with enforced quality gates

Zero manual deployment steps

Consistent and repeatable deployments

Real-world DevOps workflow implementation


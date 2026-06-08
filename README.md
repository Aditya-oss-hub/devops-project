# 🚀 DevOps CI/CD Pipeline Project

## 📌 Project Overview

This project demonstrates a complete CI/CD (Continuous Integration & Continuous Deployment) pipeline using Jenkins, Docker, and GitHub.

The goal of this project is to automate the process of building and deploying a containerized web application whenever new code is pushed to GitHub.

---

# 🛠️ Tech Stack

* Git & GitHub
* Jenkins
* Docker
* NGINX
* HTML
* CI/CD Pipeline

---

# 📂 Project Structure

```bash
devops-project/
│
├── index.html
├── Dockerfile
├── Jenkinsfile
└── README.md
```

---

# ⚙️ Project Workflow

```text
Developer
   ↓
GitHub Repository
   ↓
Jenkins Pipeline
   ↓
Docker Image Build
   ↓
Container Deployment
```

---

# 🚀 Features

✅ Automatic code pull from GitHub
✅ Docker image build automation
✅ Automatic container deployment
✅ Jenkins CI/CD pipeline
✅ Containerized web application deployment

---

# 📄 Files Explanation

## 1. index.html

Simple static website page.

---

## 2. Dockerfile

Used to create Docker image for the web application.

```dockerfile
FROM nginx:latest

COPY . /usr/share/nginx/html
```

---

## 3. Jenkinsfile

Defines the CI/CD pipeline stages.

```groovy
pipeline {

    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'YOUR_GITHUB_REPO_URL'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-project .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop docker-container || exit 0'
                bat 'docker rm docker-container || exit 0'
            }
        }

        stage('Run New Container') {
            steps {
                bat 'docker run -d -p 9090:80 --name docker-container devops-project'
            }
        }

    }
}
```

---

# 🐳 Docker Commands Used

## Build Docker Image

```bash
docker build -t devops-project .
```

## Run Docker Container

```bash
docker run -d -p 9090:80 --name docker-container devops-project
```

## Stop Container

```bash
docker stop docker-container
```

## Remove Container

```bash
docker rm docker-container
```

---

# 🔧 Jenkins Pipeline Stages

1. Clone source code from GitHub
2. Build Docker image
3. Stop old container
4. Deploy new container

---

# 🌐 Application Access

```text
http://localhost:9090
```

---

# 📚 What I Learned

* CI/CD concepts
* Jenkins pipeline creation
* Docker image and container management
* GitHub integration with Jenkins
* Deployment automation
* Basic DevOps workflow

---

# 🎯 Future Improvements

* Kubernetes deployment
* AWS EC2 hosting
* Terraform Infrastructure as Code
* Monitoring using Prometheus & Grafana
* GitHub Webhooks integration

---

# 📸 Screenshots

Add screenshots here:

* Jenkins successful build
* Docker container running
* Website output
* GitHub repository

---

# 👨‍💻 Author

Aditya Yadav

---

# ⭐ If you like this project

Give this repository a star ⭐

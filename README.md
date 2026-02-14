# 🚀 Micro CI/CD Stack (Self-Hosted)

A lightweight, production-ready DevOps platform designed for low-resource VPS (runs comfortably on **2GB RAM** even possible on **1GB RAM**). The platform suits for anyone who truely have demand in having good CI/CD while working with small resources.

Instead of relying on heavy solutions like GitLab or Jenkins, this stack provides a complete CI/CD lifecycle using **Gitea Actions**, **Docker Compose**, and a **Shared Database Architecture**.

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Gitea](https://img.shields.io/badge/Gitea-609926?style=for-the-badge&logo=gitea&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)

## ✨ Features

* **📉 Ultra-Low Footprint:** Entire stack consumes <600MB RAM idle.
* **⚡ Built-in CI/CD:** Gitea Actions (compatible with GitHub Actions) pre-configured with a Runner.
* **💾 Shared Architecture:**  Single Nginx instance for your all web apps. You can add whatever nginx config you want in config/nginx/. 
* **🐳 Docker-Native:** No Kubernetes complexity. Just pure Docker Compose.

## 🛠 Prerequisites
* A Linux VPS (Ubuntu/Debian recommended).
* Docker & Docker Compose installed.
* A domain name pointing to your server.

## 🚀 Quick Start

### 1. Initialize the Stack
Clone the repo, set up environment variables, and start the services:

```bash
git clone [https://github.com/detro1dqwe/micro-cicd-stack.git](https://github.com/detro1dqwe/micro-cicd-stack.git)
cd micro-cicd-stack
cp .env.example .env
docker compose up -d
```

### 2. Initialize the Stack
Open your browser and navigate to your domain (e.g., http://localhost:3000)
* **Register a new account.** The first registered user automatically becomes the System Administrator.

### 3. Configure the Runner (Token Setup)
To enable CI/CD pipelines, you need to generate a registration token for the runner.

1. Click on your profile avatar (top right) and select Site Administration.
![PIC!](https://i.imgur.com/e0kt1xu.png)
2. In the left menu, navigate to Actions -> Runners.
![PIC!](https://i.imgur.com/zErqQ9b.png)
3. Click the **Create new Runner** button and copy the generated token.
![PIC!](https://i.imgur.com/xHXxqL9.png)
4. Paste the token into your .env file and start the runner:
```bash
# In .env file
RUNNER_TOKEN=your_token_here
# Than
docker compose up -d gitea-runner
```
## ⚡ Performance Proof
The stack is optimized for maximum efficiency. Below is a real-world snapshot of resource usage on a 2GB RAM VPS. As you can see, the idle memory footprint for the entire ecosystem (Gitea + Runner + Nginx + Docker Registry) is incredibly low:
![PIC!](https://i.imgur.com/RDLnpW5.png)


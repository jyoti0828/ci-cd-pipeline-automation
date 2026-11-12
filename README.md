<div align="center">

# 🚀 CI/CD Pipeline Automation with Flask, Docker & GitHub Actions

**A practical CI/CD project that automates testing, Docker image building, and publishing using GitHub Actions and Docker Hub.**

</div>

---

## 📑 Table of Contents

- [📖 Project Overview](#-project-overview)
- [✨ Key Features](#-key-features)
- [🛠️ Tech Stack](#️-tech-stack)
- [🔄 CI/CD Pipeline Workflow](#-cicd-pipeline-workflow)
- [🐳 Docker Hub Repository](#-docker-hub-repository)
- [💻 Run the Application Locally](#-run-the-application-locally)
- [🔐 GitHub Actions Secrets](#-github-actions-secrets)
- [✅ Verification](#-verification)
- [🎓 Learning Outcomes](#-learning-outcomes)
- [👤 Author](#-author)

---

## 📖 Project Overview

This project demonstrates an automated CI/CD workflow for a Python Flask application. Whenever code is pushed to the `main` branch, GitHub Actions executes automated tests, builds a Docker image, and publishes it to Docker Hub. The published image can then be pulled and executed locally using Docker.

---

## ✨ Key Features

- 🌐 Flask-based REST API.
- 📦 Docker containerization for consistent application execution.
- 🧪 Automated testing using pytest.
- ⚙️ GitHub Actions workflow for CI/CD automation.
- 🏗️ Automated Docker image building.
- 🚢 Docker Hub integration for image publishing.
- 🏷️ Commit-specific and `latest` Docker image tags.
- ▶️ Local container execution and verification.

---

## 🛠️ Tech Stack

| Category | Technologies |
| :--- | :--- |
| 🐍 Programming Language | Python |
| 🌶️ Backend Framework | Flask |
| 🧪 Testing | pytest |
| 📦 Containerization | Docker |
| ⚙️ CI/CD | GitHub Actions |
| 🗄️ Container Registry | Docker Hub |
| 🔧 Version Control | Git, GitHub |

---

## 🔄 CI/CD Pipeline Workflow

The pipeline is defined in `.github/workflows/ci-cd.yml`.

### 📍 Pipeline Stages

1. **📤 Code Push:** Developer pushes code to the `main` branch.
2. **🧪 Automated Testing:** GitHub Actions checks out the repository, sets up Python, installs dependencies, and executes tests using pytest.
3. **🏗️ Docker Image Build:** Runs after successful tests and builds the Flask application Docker image.
4. **🚢 Docker Hub Publishing:** Authenticates using GitHub repository secrets and publishes the image with `latest` and commit-specific tags.

### 🧭 Pipeline Architecture

```text
Developer
    |
    | Push code to GitHub
    v
GitHub Actions
    |
    v
Run Automated Tests (pytest)
    |
    | Tests Pass
    v
Build Docker Image
    |
    v
Push Image to Docker Hub
    |
    v
Pull and Run Container Locally
```

---

## 🐳 Docker Hub Repository

**Docker image:** `patrajyoti8/flask-docker-app`

🔗 [View Docker Hub Repository](https://hub.docker.com/r/patrajyoti8/flask-docker-app)

**Available tags:**

- `latest`
- Commit-specific SHA tag

---

## 💻 Run the Application Locally

### 📋 Prerequisites

- Python
- Docker Desktop
- Git

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/jyoti0828/ci-cd-pipeline-automation.git
cd ci-cd-pipeline-automation
```

### 2️⃣ Pull the Docker Image

```bash
docker pull patrajyoti8/flask-docker-app:latest
```

### 3️⃣ Run the Container

```bash
docker run -d -p 5000:5000 --name flask-app patrajyoti8/flask-docker-app:latest
```

### 4️⃣ Access the Application

Open your browser at `http://localhost:5000`.

Expected response:

```json
{
  "env": "production",
  "host": "<container-hostname>",
  "message": "Hello from Flask + Docker!"
}
```

### 5️⃣ Stop the Container

```bash
docker stop flask-app
docker rm flask-app
```

---

## 🔐 GitHub Actions Secrets

The workflow uses GitHub repository secrets for Docker Hub authentication.

| Secret | Purpose |
| :--- | :--- |
| `DOCKER_HUB_USERNAME` | Docker Hub username |
| `DOCKER_HUB_TOKEN` | Docker Hub access token |

> 🔒 Sensitive credentials are stored securely in GitHub Actions Secrets rather than hardcoded in the workflow.

---

## ✅ Verification

The following components have been tested successfully:

- ✔️ Automated pytest execution through GitHub Actions.
- ✔️ Successful Docker image build.
- ✔️ Successful image publishing to Docker Hub.
- ✔️ Successful Docker image pull on a local machine.
- ✔️ Successful container startup.
- ✔️ Flask application response through `localhost:5000`.

---

## 🎓 Learning Outcomes

- 💡 Understanding CI/CD pipeline automation.
- 💡 Configuring GitHub Actions workflows.
- 💡 Automating Python application testing.
- 💡 Building and managing Docker images.
- 💡 Publishing container images to Docker Hub.
- 💡 Running and verifying containerized applications locally.
- 💡 Managing credentials using GitHub repository secrets.

---

## 👤 Author

**Jyoti Patra**

🐙 GitHub: [jyoti0828](https://github.com/jyoti0828)

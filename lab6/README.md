# Flask Deployment Demo

![Build and Deploy](https://github.com/YOUR_GITHUB_USERNAME/flask-deployment-demo/workflows/Build%20and%20Deploy/badge.svg)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat&logo=docker&logoColor=white)
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=flat&logo=flask&logoColor=white)

A demonstration of automated Docker deployment with GitHub Actions, environments, and approval workflows.

## Features

- 🚀 **Automated Deployment**: Push to main triggers staging deployment
- 🔒 **Environment Protection**: Production requires manual approval
- 🐳 **Docker**: Containerized application with multi-platform builds
- 🔄 **Rollback**: Manual rollback workflow for quick recovery
- 📊 **Monitoring**: Health checks and deployment status
- 🌍 **Multi-Environment**: Staging and Production environments

## Environments

- **Staging**: Auto-deployed on main branch push
- **Production**: Requires manual approval after staging success

## Docker Repository

- **DockerHub**: [YOUR_DOCKERHUB_USERNAME/flask-deployment-demo](https://hub.docker.com/r/YOUR_DOCKERHUB_USERNAME/flask-deployment-demo)

## Manual Deployment

To deploy manually:

1. Go to **Actions** tab
2. Select **Build and Deploy** workflow
3. Click **Run workflow**
4. Choose environment and options
5. Click **Run workflow**

## Rollback

To rollback a deployment:

1. Go to **Actions** tab
2. Select **Rollback Deployment** workflow
3. Click **Run workflow**
4. Choose environment and previous version
5. Click **Run workflow**

## Local Development

```bash
# Run locally
pip install -r requirements.txt
python app.py

# Run with Docker
docker build -t flask-demo .
docker run -p 8080:5000 flask-demo
```

## Deployment Flow

```
Push to main → Tests → Build Image → Deploy Staging → (Approval) → Deploy Production
```

## Endpoints

- `/` - Home page with deployment information
- `/health` - Health check endpoint
- `/version` - Version information

## Setup Instructions

### Prerequisites

1. GitHub account
2. DockerHub account
3. Docker installed locally

### Configuration Steps

1. **Create GitHub Repository**
   - Create a new repository named `flask-deployment-demo`
   - Push this code to the repository

2. **Set up GitHub Environments**
   - Go to Settings → Environments
   - Create `staging` environment (no approval required)
   - Create `production` environment (with required reviewers)

3. **Configure Secrets**
   - Repository secrets:
     - `DOCKERHUB_USERNAME`: Your DockerHub username
     - `DOCKERHUB_TOKEN`: Your DockerHub access token
   - Environment secrets (for staging and production):
     - `DOCKER_REGISTRY`: docker.io
     - `DEPLOY_URL`: Your deployment URL

4. **Test Locally**
   ```bash
   # Test application
   pip install -r requirements.txt
   python app.py
   
   # Test with Docker
   docker build -t flask-demo .
   docker run -p 8080:5000 flask-demo
   ```

5. **Deploy**
   - Push to main branch to trigger automatic deployment
   - Or use manual workflow dispatch for controlled deployments

## Lab 6 Notes

This project is part of Lab 6: Automate Docker Image Deployment with GitHub Actions.

**Replace the following placeholders:**
- `YOUR_GITHUB_USERNAME` with your actual GitHub username
- `YOUR_DOCKERHUB_USERNAME` with your actual DockerHub username

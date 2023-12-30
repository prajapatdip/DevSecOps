# DevSecOps CI/CD Pipeline Project

## Overview

This project focuses on implementing a robust DevSecOps CI/CD pipeline using Jenkins, SonarQube, Trivy, ArgoCD, and Docker, with deployment on AWS services.


## Pipeline Process

#### 1. Code Commit and Jenkins Trigger:
- Code changes are committed to the GitHub repository.
- Jenkins monitors the repository for changes.
- Upon a commit, Jenkins initiates the CI/CD pipeline.

#### 2. SonarQube Testing:

- Jenkins triggers SonarQube analysis to ensure code quality and security.
- SonarQube provides insights and identifies potential vulnerabilities in the code.

#### 3. Docker Image Build:

- Jenkins builds a Docker image incorporating the code changes.
- The Docker image is scanned for vulnerabilities using Trivy.

#### 4. Docker Image Deployment to Docker Hub:

- Jenkins deploys the Docker image to Docker Hub.
- The image is versioned and tagged for traceability.

#### 5. ArgoCD for Kubernetes Deployment:

- ArgoCD monitors the manifest repository for changes.
- If there are changes in the manifest repository (e.g., Kubernetes YAML files), - - ArgoCD applies the changes to the AWS Kubernetes cluster.

#### 6. Monitoring with Prometheus and Grafana:

- Prometheus is configured to scrape metrics from Jenkins, Docker, and the Kubernetes cluster.
- Grafana dashboards provide real-time monitoring and visualization of Jenkins builds, Docker image vulnerabilities, and Kubernetes cluster health.

#### 7. AWS Services:

- The entire pipeline is built and deployed on AWS services.
- AWS is leveraged for hosting Jenkins, SonarQube, Docker Hub, ArgoCD, Prometheus, Grafana, and the Kubernetes cluster.
## Setup Instructions

#### 1. Jenkins Setup:

- Install Jenkins on an AWS instance.
- Configure Jenkins with the necessary plugins.
- Set up Jenkins credentials for GitHub and Docker Hub.

#### 2. SonarQube Setup:

- Install SonarQube on an AWS instance.
- Configure SonarQube and integrate it with Jenkins.

#### 3. Trivy Setup:

- Integrate Trivy into the Jenkins pipeline for Docker image scanning.

#### 4. ArgoCD Setup:

- Deploy ArgoCD on the AWS Kubernetes cluster.
- Configure ArgoCD to watch the manifest repository and sync changes.

#### 5. Monitoring Setup:

- Deploy Prometheus and Grafana on the AWS Kubernetes cluster.
- Configure Prometheus to scrape metrics from Jenkins, Docker, and the Kubernetes cluster.
- Import Grafana dashboards for Jenkins, Docker, and Kubernetes monitoring.

#### 6. AWS Services Setup:

- Set up AWS services such as EKS for the Kubernetes cluster.

#### 7. GitHub Webhook:

- Configure a webhook in the GitHub repository to trigger Jenkins on code changes.

## Run Locally

__1. Locally:__

```
    git clone https://github.com/prajapatdip/Cloud-Native-Monitoring-App.git
    cd Cloud-Native-Monitoring-App
```

```
    docker build --build-arg TMDB_V3_API_KEY=<your-api-key> -t netflix
```

```
    docker run -d -p 80:80 netflix:latest
```
# MicroserviceLab – CI/CD Pipeline with Jenkins, Docker, Amazon ECR, and Kubernetes

MicroserviceLab is a cloud computing project that demonstrates the automation of building, containerizing, and deploying a microservice application using a CI/CD pipeline. The source code is stored in GitHub, Jenkins automates the pipeline, Docker builds the application image, and Amazon Elastic Container Registry (ECR) stores the image. The application is deployed locally on a Minikube Kubernetes cluster using Deployment and NodePort Service configurations.

## Technologies Used
- **GitHub** – Source code management
- **Jenkins** – CI/CD pipeline automation
- **Docker** – Containerization
- **Amazon ECR** – Container image registry
- **Kubernetes** – Container orchestration
- **Minikube** – Local Kubernetes cluster

## Pipeline Workflow
1. Source code is stored in the GitHub repository.
2. Jenkins checks out the latest code from the `main` branch.
3. Jenkins builds the Docker image using the `Dockerfile`.
4. The Docker image is pushed to Amazon ECR.
5. The image is loaded into Minikube.
6. Kubernetes deploys the application using the Deployment and NodePort Service.
7. Pods, Deployment, Service, and application accessibility are verified.

## Repository Structure
- `backend/` – Application source code
- `Dockerfile` – Docker image build instructions
- `Jenkinsfile` – Jenkins pipeline definition
- `deployment.yaml` – Kubernetes Deployment configuration
- `service.yaml` – Kubernetes Service configuration
- `README.md` – Project documentation

## Deployment Details
- **Jenkins Job:** `MicroserviceLab`
- **ECR Repository:** `student-service`
- **Kubernetes Deployment:** `studentapp-deployment`
- **Kubernetes Service:** `studentapp-service`
- **Deployment Replicas:** 4
- **Service Type:** NodePort
- **NodePort:** `30007`

## Objective
The objective of this project is to understand CI/CD automation, Docker image management, and Kubernetes deployment by integrating development and deployment tools into a single workflow.

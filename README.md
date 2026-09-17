# Node.js Docker CI/CD with Jenkins

This project demonstrates a simple CI/CD pipeline for a Node.js application using:

- Node.js
- Docker
- Jenkins
- GitHub
- Docker Hub

## Project Structure

NodeJs-Docker/
│
├── nodejs-cicd/
│   ├── Dockerfile
│   ├── app.js
│   ├── package.json
│   └── Jenkinsfile
│
└── README.md

## CI/CD Workflow

GitHub
   |
   v
Jenkins
   |
   v
Checkout Code
   |
   v
Build Docker Image
   |
   v
Docker Hub Login
   |
   v
Push Image to Docker Hub
   |
   v
Pull Latest Image
   |
   v
Deploy Docker Container

## Docker

The Dockerfile is located inside:

nodejs-cicd/Dockerfile

The Docker image is built using:

cd nodejs-cicd
docker build -t <DOCKERHUB_USERNAME>/nodejs-cicd:latest .

## Docker Container

The Node.js application runs on port: 3000

The container is deployed using:

docker run -d \
  --name nodejs-app \
  -p 3000:3000 \
  <DOCKERHUB_USERNAME>/nodejs-cicd:latest

## Jenkins Pipeline

The Jenkinsfile is located inside the `nodejs-cicd` directory.

The pipeline performs the following stages:

1. Checkout code from GitHub
2. Build the Docker image
3. Authenticate with Docker Hub
4. Push the image to Docker Hub
5. Stop the existing container
6. Remove the existing container
7. Pull the latest image
8. Deploy the new container

## Docker Image

<DOCKERHUB_USERNAME>/nodejs-cicd:latest

## Application Access

After successful deployment:

http://<SERVER_IP>:3000

If running on an AWS EC2 instance, ensure port 3000 is allowed in the Security Group.

## Useful Docker Commands

Check Docker images: docker images

Check running containers: docker ps

View application logs: docker logs nodejs-app

Stop container: docker stop nodejs-app

Remove container: docker rm nodejs-app

## Security

Docker Hub credentials are stored securely in Jenkins Credentials.

Passwords, access tokens, and other secrets should never be committed to GitHub.

## DevOps Concepts

This project demonstrates:

- Git
- GitHub
- Jenkins CI/CD
- Docker
- Docker Hub
- Container deployment
- Jenkins Credentials
- Linux shell commands
- Automated deployment

## Author

**Kruthik Reddy**

DevOps Engineer

Azure | AWS | Docker | Kubernetes | Jenkins | Terraform | CI/CD

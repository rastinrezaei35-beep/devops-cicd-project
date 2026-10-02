# Jenkins Docker CI/CD Pipeline

A simple CI/CD project that automatically builds and deploys a Dockerized Nginx web application using Jenkins, GitHub, and Docker.

## Architecture

Developer
   |
   | git push
   v
GitHub
   |
   | Poll SCM
   v
Jenkins
   |
   | Docker Build
   v
Docker Image
   |
   | Deploy
   v
Docker Container
   |
   v
Nginx Web Server

## Technologies

- Linux
- Git
- GitHub
- Jenkins
- Docker
- Dockerfile
- Nginx
- Shell Script

## Project Structure

devops-cicd-project/
├── index.html
├── Dockerfile
└── README.md

## Dockerfile

The application uses Nginx Alpine as the base image.

The HTML application is copied into:

/usr/share/nginx/html/index.html

## CI/CD Process

1. Developer changes the application code.
2. Changes are committed using Git.
3. Changes are pushed to GitHub.
4. Jenkins detects the changes using Poll SCM.
5. Jenkins checks out the latest source code.
6. Jenkins builds a new Docker image.
7. Jenkins stops the previous container.
8. Jenkins removes the previous container.
9. Jenkins starts a new container.
10. The updated application becomes available.

## Docker Commands

Build image:

docker build -t devops-cicd-project:latest .

Run container:

docker run -d \
  --name devops-cicd-container \
  -p 8082:80 \
  devops-cicd-project:latest

Test application:

curl http://localhost:8082

## CI/CD Deployment

The Jenkins job executes the following deployment process:

docker build
↓
stop old container
↓
remove old container
↓
run new container

## Learning Objectives

This project demonstrates practical experience with:

- Git version control
- GitHub repository management
- Jenkins CI/CD
- Docker image creation
- Docker container deployment
- Nginx
- Linux command line
- Automated application deployment

### Basic Static Web App – CI/CD Pipeline Project ###
This project demonstrates a complete DevOps CI/CD pipeline for a simple static web application using Git, GitHub, Jenkins, and Docker.

### Project Overview ###
Application: Basic static HTML web page
CI/CD Tools: Git, GitHub, Jenkins, Docker, Docker Hub
Workflow:
Git → GitHub → Jenkins → Docker Build → Docker Hub
This project showcases:
Version control with Git and GitHub
Automated build and deployment using Jenkins
Containerization with Docker
End-to-end CI/CD pipeline

### Prerequisites ###
Git installed
GitHub account
Jenkins server with Docker plugin
Docker Hub account
Basic command-line knowledge

### Getting Started ###
1. Clone the Repository
Eg: git clone https://github.com/yourusername/basic-static-web-app.git
Eg: cd basic-static-web-app
2. Build and Run Locally
Eg: docker build -t yourusername/basic-static-web-app:latest .
Eg: docker run -d -p 8080:80 yourusername/basic-static-web-app:latest

3. CI/CD Pipeline Setup
Push your code to GitHub.
Configure a Jenkins pipeline job to use your GitHub repository.
Set up Docker Hub credentials in Jenkins.
Trigger the pipeline to build and push the Docker image.
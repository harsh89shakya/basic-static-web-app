pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "harsh89shakya/basic-static-web-app"
        DOCKER_CREDS = credentials('docker-hub-cred')
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/harsh89shakya/basic-static-web-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat "docker build -t %DOCKER_IMAGE%:latest ."
            }
        }

        stage('Login to Docker Hub') {
            steps {
                bat "docker login -u %DOCKER_CREDS_USR% -p %DOCKER_CREDS_PSW%"
            }
        }

        stage('Push Docker Image') {
            steps {
                bat "docker push %DOCKER_IMAGE%:latest"
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
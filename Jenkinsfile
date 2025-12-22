pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "harsh89shakya/basic-static-web-app"
        DOCKER_CREDS = credentials('docker-hub-cred')
    }

    stages {

        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/harsh89shakya/basic-static-web-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t $DOCKER_IMAGE:latest ."
            }
        }

        stage('Login to Docker Hub') {
            steps {
                sh "docker login -u ${DOCKER_CREDS_USR} -p ${DOCKER_CREDS_PSW}"
            }
        }

        stage('Push Docker Image') {
            steps {
                sh "docker push $DOCKER_IMAGE:latest"
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
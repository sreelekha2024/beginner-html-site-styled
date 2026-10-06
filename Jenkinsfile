pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/sreelekha2024/beginner-html-site-styled.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sreelekha10/html-app:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push sreelekha10/html-app:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}

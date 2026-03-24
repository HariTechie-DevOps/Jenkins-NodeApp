pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/HariTechie-DevOps/Jenkins-NodeApp.git'
            }
        }

        stage('Stop Old Containers') {
            steps {
                sh 'docker-compose down || true'
            }
        }

        stage('Build & Deploy') {
            steps {
                sh 'docker-compose up -d --build'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }
}

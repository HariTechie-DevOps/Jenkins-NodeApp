pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/HariTechie-DevOps/Jenkins-NodeApp.git'
            }
        }

        stage('Stop & Clean Old Containers') {
            steps {
                sh '''
                docker-compose down || true
                docker rm -f resume-backend resume-frontend || true
                '''
            }
        }

        stage('Build & Deploy') {
            steps {
                sh '''
                docker-compose up -d --build
                '''
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }
}

pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/HariTechie-DevOps/Jenkins-NodeApp.git'
            }
        }

        stage('Build Backend Image') {
            steps {
                sh 'docker build -t resume-backend ./server'
            }
        }

        stage('Build Frontend Image') {
            steps {
                sh 'docker build -t resume-frontend ./client'
            }
        }

        stage('Run Containers') {
            steps {
                sh '''
                docker run -d -p 5000:5000 --name resume-backend resume-backend
                docker run -d -p 3000:3000 --name resume-frontend resume-frontend
                '''
            }
        }
    }
}

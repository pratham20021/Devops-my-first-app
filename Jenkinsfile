pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/pratham20021/Devops-my-first-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-first-app .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker stop my-first-app || true'
                sh 'docker rm my-first-app || true'
                sh 'docker run -d -p 5000:5000 --name my-first-app my-first-app'
            }
        }
    }
}

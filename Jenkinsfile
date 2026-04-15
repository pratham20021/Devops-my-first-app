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
                bat 'docker build -t my-first-app .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker stop my-first-app || exit 0'
                bat 'docker rm my-first-app || exit 0'
                bat 'docker run -d -p 5000:5000 --name my-first-app my-first-app'
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                echo 'Code cloned from GitHub'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker stop myapp-container || true'
                sh 'docker rm myapp-container || true'
                sh 'docker run -d -p 80:80 --name myapp-container myapp:latest'
            }
        }
    }
}

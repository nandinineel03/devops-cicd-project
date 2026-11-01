pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                sh 'test -f index.html'
                echo 'Application test successful'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-cicd-web:latest .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker rm -f devops-web || true
                    docker run -d --name devops-web --restart unless-stopped -p 80:80 devops-cicd-web:latest
                '''
            }
        }
    }
}

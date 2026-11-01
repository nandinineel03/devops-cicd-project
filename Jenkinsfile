pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Application'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f index.html'
                echo 'Application test successful'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage completed'
            }
        }
    }
}

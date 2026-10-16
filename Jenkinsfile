pipeline {
    agent any

    environment {
        DUMMY_CLOUD_KEY = credentials('dummy-cloud-key')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building application..."'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running test suite..."'
                sh 'echo "All tests passed"'
            }
        }
        stage('Deploy (simulated)') {
            steps {
                sh 'echo "Deploying with service account credential (value masked by Jenkins)"'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
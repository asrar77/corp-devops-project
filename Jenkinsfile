pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo '✅ Checking out code from GitHub...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo '📦 Installing Python dependencies...'
                sh 'python3 -m pip install --upgrade pip'
                sh 'python3 -m pip install -r app/requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                echo '🧪 Running Python tests...'
                sh 'pytest tests/'
            }
        }
    }

    post {
        success {
            echo '🎉 Pipeline succeeded! All tests passed!'
        }
        failure {
            echo '❌ Pipeline failed! Check logs!'
        }
    }
}

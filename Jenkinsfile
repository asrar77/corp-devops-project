pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Python dependencies...'
                // On Windows use 'bat', on Linux use 'sh'
                bat 'python -m pip install --upgrade pip'
                bat 'python -m pip install -r app/requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running Python tests...'
                bat 'pytest tests/'
            }
        }
    }

    post {
        success {
            echo '✅ All tests passed!'
        }
        failure {
            echo '❌ Tests failed — check logs!'
        }
    }
}

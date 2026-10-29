
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Source code checkout completed'
            }
        }

        stage('Build') {
            steps {
                bat 'echo Building the application...'
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                bat 'if exist README.md (echo TEST PASSED: README.md found) else (echo TEST FAILED: README.md missing & exit /b 1)'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check Console Output.'
        }
    }
}

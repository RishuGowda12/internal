
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Checking Python application'
                bat 'python --version'
                bat 'python -m py_compile python.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Executing automated tests'
                bat 'python -m unittest'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running Python application'
                bat 'python python.py'
            }
        }
    }

    post {
        success {
            echo 'CI Pipeline completed successfully'
        }

        failure {
            echo 'CI Pipeline failed'
        }
    }
}

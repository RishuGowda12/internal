
pipeline {
    agent any

    environment {
        PYTHON = 'C:\\Users\\STUDENT\\AppData\\Local\\Programs\\Python\\Python313\\python.exe'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Checking Python application'
                bat '"%PYTHON%" --version'
                bat '"%PYTHON%" -m py_compile python.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Executing automated tests'
                bat '"%PYTHON%" -m unittest'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running Python application'
                bat '"%PYTHON%" python.py'
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

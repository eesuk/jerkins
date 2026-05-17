pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: '<URL>', branch: 'main'
            }
        }

        stage('Install') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                bat 'pytest'
            }
        }
    }
}
pipeline {
    agent any

    environment {
        PYTHON = "C:\\Users\\gulag\\AppData\\Local\\Python\\bin\\python.exe"
    }

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/eesuk/jerkins.git', branch: 'master'
            }
        }

        stage('Debug workspace') {
            steps {
                bat 'dir'
            }
        }

        stage('Check Python') {
            steps {
                bat '"%PYTHON%" --version'
                bat '"%PYTHON%" -c "import sys; print(sys.executable)"'
            }
        }

        stage('Install dependencies') {
            steps {
                bat '"%PYTHON%" -m pip install --upgrade pip'
                bat '"%PYTHON%" -m pip install -r requirements.txt || exit 1'
                bat '"%PYTHON%" -m pip list'
            }
        }

        stage('Run tests') {
            steps {
                bat '"%PYTHON%" -m pytest -v || exit 1'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished'
        }
    }
}
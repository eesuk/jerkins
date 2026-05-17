pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/eesuk/jerkins.git', branch: 'master'
            }
        }

        stage('Install') {
            steps {
                bat '"C:\\Users\\gulag\\AppData\\Local\\Python\\bin\\python.exe" -m pip install --upgrade pip'
                bat '"C:\\Users\\gulag\\AppData\\Local\\Python\\bin\\python.exe" -m pip install -r requirements.txt'
                bat '"C:\\Users\\gulag\\AppData\\Local\\Python\\bin\\python.exe" -m pip list'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\\Users\\gulag\\AppData\\Local\\Python\\bin\\python.exe" -m pytest -v'
            }
        }
    }
}
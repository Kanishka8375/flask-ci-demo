pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Kanishka8375/flask-ci-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh './venv/bin/python -m unittest discover tests'
            }
        }

        stage('Run Flask App') {
            steps {
                sh './venv/bin/python app.py'
            }
        }
    }
}

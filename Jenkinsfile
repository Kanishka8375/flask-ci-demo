pipeline {
    agent any

    stages {
        stage('Create Virtual Environment') {
            steps {
                sh 'python3 -m venv venv'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
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

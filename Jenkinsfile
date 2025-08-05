pipeline {
    agent any

    environment {
        PATH = "K:\\Git\\bin;${env.PATH}"
    }

    stages {
        stage('Create Virtual Environment') {
            steps {
                bat 'python -m venv venv'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '.\\venv\\Scripts\\pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                bat '.\\venv\\Scripts\\python -m unittest discover tests'
            }
        }

        stage('Run Flask App') {
            steps {
                bat '.\\venv\\Scripts\\python app.py'
            }
        }
    }
}

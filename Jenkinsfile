pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                bat 'python -m venv venv'
                bat '.\\venv\\Scripts\\pip install -r requirements.txt'
            }
        }

        stage('Run unit tests') {
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

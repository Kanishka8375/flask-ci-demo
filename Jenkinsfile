pipeline {
    agent any

    environment {
        PYTHON = 'C:\\Python311\\python.exe' // replace with actual path if different
        PIP = 'C:\\Python311\\Scripts\\pip.exe'
    }

    stages {
        stage('Create Virtual Environment') {
            steps {
                bat "${PYTHON} -m venv venv"
            }
        }

        stage('Install Dependencies') {
            steps {
                bat ".\\venv\\Scripts\\pip install -r requirements.txt"
            }
        }

        stage('Run Unit Tests') {
            steps {
                bat ".\\venv\\Scripts\\python -m unittest discover tests"
            }
        }

        stage('Run Flask App') {
            steps {
                bat ".\\venv\\Scripts\\python app.py"
            }
        }
    }
}

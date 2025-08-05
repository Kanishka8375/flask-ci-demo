pipeline {
    agent any

    stages {
        stage('Setup and Run') {
            steps {
                bat '''
                    python -m venv venv
                    venv\\Scripts\\pip install -r requirements.txt
                    venv\\Scripts\\python -m unittest discover tests
                    venv\\Scripts\\python app.py
                '''
            }
        }
    }
}

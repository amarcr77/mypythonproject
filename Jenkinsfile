pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Use your local repo or GitHub URL
                git 'https://github.com/amarcr77/mypythonproject.git'
            }
        }

        stage('Setup Python') {
            steps {
                bat 'python -m venv venv'
                bat '.\\venv\\Scripts\\activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat '.\\venv\\Scripts\\activate && python test_app.py'
            }
        }

        stage('Run App') {
            steps {
                bat '.\\venv\\Scripts\\activate && python app.py'
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
                // Install flake8 for linting
                sh './venv/bin/pip install flake8'
            }
        }
        stage('Lint') {
            steps {
                // This checks your code for errors
                sh './venv/bin/flake8 tests/ --count --select=E9,F63,F7,F82 --show-source --statistics'
            }
        }
        stage('Test') {
            steps {
                sh './venv/bin/python -m pytest --junitxml=report.xml'
            }
        }
    }
    post {
        always {
            junit 'report.xml'
        }
    }
}

pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Now that python3-venv is installed, this will succeed
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh './venv/bin/python -m pytest'
            }
        }
    }
}

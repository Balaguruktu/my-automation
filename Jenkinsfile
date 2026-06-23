pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Ensure pip is installed if not present
                sh 'python3 -m ensurepip --upgrade'
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
    }
}

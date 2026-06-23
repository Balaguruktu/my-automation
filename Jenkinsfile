pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // 1. Create a virtual environment named 'venv'
                sh 'python3 -m venv venv'
                
                // 2. Install requirements using the pip inside the venv
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                // 3. Run pytest using the python binary inside the venv
                sh './venv/bin/python -m pytest'
            }
        }
    }
}

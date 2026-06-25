pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Creating virtual environment...'
                // If on Windows, use bat 'python -m venv venv'
                sh 'python3 -m venv venv'
                
                echo 'Installing requirements...'
                // If on Windows, the path is .\venv\Scripts\pip
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        
        stage('Run Tests') {
            steps {
                echo 'Running pytest for new feature...'
                // Using the exact path and file that you confirmed works
                sh './venv/bin/pytest tests/test_new_feature.py -v'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline execution complete.'
        }
    }
}
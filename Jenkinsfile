pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Creating virtual environment...'
                sh 'python3 -m venv venv'
                
                echo 'Installing requirements...'
                // Using standard Linux path
                sh './venv/bin/pip install --upgrade pip'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        
        stage('Debug Workspace') {
            steps {
                echo 'Listing workspace files to verify test file exists...'
                // This is crucial: it shows us if 'tests/test_new_feature.py' is actually there
                sh 'ls -R' 
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running pytest...'
                // Run the specific test file
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

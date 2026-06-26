pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Creating virtual environment...'
                bat 'python -m venv venv'
                
                echo 'Installing requirements...'
                // On Windows, the pip executable is in the Scripts folder
                bat 'venv\\Scripts\\pip install -r requirements.txt'
            }
        }
        
        stage('Run Tests') {
            steps {
                echo 'Running pytest...'
                // Using the Windows-style path to pytest
                bat 'venv\\Scripts\\pytest tests/test_new_feature.py -v'
            }
        }
    }
}

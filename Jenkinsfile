pipeline {
    agent any

    stages {
        stage('Setup and Install') {
            steps {
                echo 'Ensuring clean environment...'
                // Use absolute paths or verify the current directory
                script {
                    bat 'if exist venv rmdir /s /q venv'
                    bat 'python -m venv venv'
                    bat 'venv\\Scripts\\python -m pip install --upgrade pip'
                    bat 'venv\\Scripts\\pip install -r requirements.txt'
                }
            }
        }
        
        stage('Run Tests') {
            steps {
                echo 'Running pytest...'
                // Use the absolute path to the Python executable in the venv
                bat 'venv\\Scripts\\pytest tests/test_new_feature.py -v'
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Setup and Debug') {
            steps {
                // 1. Debug: Show us exactly where we are
                bat 'echo Current directory is: %CD%'
                bat 'dir'
                
                // 2. Setup: Create venv and force-install pip
                bat 'python -m venv venv'
                bat 'venv\\Scripts\\python -m ensurepip'
                bat 'venv\\Scripts\\python -m pip install --upgrade pip'
                bat 'venv\\Scripts\\pip install -r requirements.txt'
            }
        }
        
        stage('Run Tests') {
            steps {
                // 3. Run: Use the full path to the python executable in the venv
                bat 'venv\\Scripts\\pytest.exe tests/test_new_feature.py -v'
            }
        }
    }
}

pipeline {
    agent any
    
    stages {
        stage('Rocking') {
            steps {
                echo 'Building...'
            }
        }
        stage('Roasting') {
            steps {
                echo 'Running tests...'
                // If you want to run your python test:
                // sh 'python3 -m pytest tests/test_demo.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}

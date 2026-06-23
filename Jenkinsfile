pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                // We add --junitxml=report.xml so pytest creates the file
                sh './venv/bin/python -m pytest --junitxml=report.xml'
            }
        }
    }
    
    // The post block must be at the pipeline level, outside of stages
    post {
        always {
            // This reads the file created by the command above
            junit 'report.xml'
        }
    }
}

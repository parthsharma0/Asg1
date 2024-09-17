pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    bat 'python3 -m venv venv'
                    bat 'venv/bin/pip install -r requirements.txt'
                }
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    bat 'venv/bin/pytest --junitxml=report.xml'
                }
            }
        }
    }
    post {
        always {
            junit '**/report.xml'  // Ensure this matches the location of your test reports
        }
    }
}

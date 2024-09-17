pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                          sh 'python -m venv venv'
                          sh 'venv\\Scripts\\pip install -r requirements.txt'
                       }
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    sh 'venv/bin/pytest --junitxml=report.xml'
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

pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'python -m pip install --upgrade pip'
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Pytest') {
            steps {
                bat 'pytest -v'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'All tests passed ✅'
        }
        failure {
            echo 'Tests failed ❌'
        }
    }
}

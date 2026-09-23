pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Run Unit Tests') {
            steps {
                bat 'pytest'
            }
        }
    }
    post {
        success {
            echo 'Build succeeded! All tests passed.'
        }
        failure {
            echo 'Build failed! Please check the test logs.'
        }
    }
}

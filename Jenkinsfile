pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/harshmishra170206/basic.git']])
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

pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' alwaysPull true }
    }
    stages {
        stage('Test') {
            steps {
                sh 'echo hello'
                sh 'node --version'
            }
        }
    }
}

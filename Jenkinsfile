pipeline {
    agent {
        docker { image 'node:14.0.0-alpine'}
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}

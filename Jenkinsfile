pipeline {
    //agent any
    agent {
        docker { image 'node:14-alpine'}
    }
    stages {
        stage('Git checkout') {
            steps {
                // Get source code from a GitHub repository
                git branch:'main', url:'https://github.com/OYANG21/GoExpertsFrontend'
                
            }
        }
        
        stage('npm install'){
            steps {
                dir("./") {
                    sh 'npm install'
                    sh 'pwd'
                }
            }
        }
        
        stage('npm build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}

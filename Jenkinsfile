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
                }
            }
        }
        
        stage('npm build') {
            steps {
                dir("./") {
                    sh 'npm run build'
                }
            }
        }
        
        stage('syn s3') {
            steps {
                dir("./build") {
                    // sh 'aws s3 sync build s3://goexperts'
                    pwd();
                    withAWS(region:'ap-southeast-2', credentials:'818255485773'){
                        // def identity=awsIdentity();
                        s3Upload(bucket:"goexperts", workingDir:'dist', includePathPattern:'**/*');
                    }
                }
            }
        }
    }
}

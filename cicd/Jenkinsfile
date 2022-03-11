pipeline {
    agent {
        docker {
            image 'node:16.13.1-alpine'

        }
    }
       stages {
        stage('Git checkout') {
            steps{
                // Get source code from a GitHub repository
                git branch:'main', url:'https://github.com/OYANG21/GoExpertsFrontend'
            }
        }
        
        stage('npm install') {
            steps{
                // install dependence
                dir("./") {
                    sh 'npm install'
                    sh 'echo hello'
                }
            }
        }
        
      

        post {
            always { 
                echo 'I will always say Hello again!'
            }
        }
    }
}

pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim' 
            args '-p 8080:8080' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm build' 
            }
        }
    }
}

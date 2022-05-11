pipeline {
    agent {
        docker {
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

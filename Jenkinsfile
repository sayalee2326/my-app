pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'npm install'
            sh 'npm run build'
          }
        }
      }
    }
  }
}

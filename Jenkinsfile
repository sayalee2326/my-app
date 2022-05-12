pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'npm start'
            sh 'npm run build'
          }
        }
      }
    }
  }
}

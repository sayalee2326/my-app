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
    stage('Deploy') {
      parallel {
        stage('Deploy'){
          steps {
            sh "aws configure set region $AWS_DEFAULT_REGION" 
            sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
            sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID" 
            sh "pwd"
            sh "aws s3 cp /home/excellarate/Downloads/exc1.png s3://mystaticdemosite"
                }
              }
           }
          }          
        }
      }
    }
  }
}
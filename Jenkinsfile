pipeline{
    agent any
    stages {
        stage('build') {
        parallel {
            stage('Build') {
            steps {
              sh 'npm install'
              sh 'npm run build'
            }
    }
  }
            stage('deploy') {
            steps {
                sh "aws configure set region $AWS_DEFAULT_REGION" 
                sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
                sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID" 
                sh "pwd"
            }
    }
}
}
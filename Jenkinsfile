pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                parallel(
                        sh 'npm install'
                        sh 'npm run build'
                )
            }
        }
        stage('Push to S3') {
            steps {
                parallel(
                        sh "aws configure set region $AWS_DEFAULT_REGION" 
                        sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
                        sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID" 
                        sh "pwd"
            
                
                )
            }
        }
    }
}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }      
        stage('S3 & Invalidations') {
             steps {
                 withAWS(region:'us-east-1',credentials:'1234') {
                 sh 'echo "Uploading content with AWS creds"'
                    s3Upload(bucket:"mystaticdemosite", includePathPattern:'**/*', workingDir:'build')
                    cfInvalidate(distribution:'EPDQY3PL7FDWB', paths:['/*'], waitForCompletion: true)
                 }   
             }
        }
    }
}
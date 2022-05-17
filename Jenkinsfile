pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }      
        stage('Upload to AWS') {
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
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
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'https://github.com/sayalee2326/my-app.git', bucket:'mystaticdemosite')

                 }   
             }
        }
    }
}
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
                 s3Upload acl: 'Private', bucket: 'mystaticdemosite', cacheControl: '', excludePathPattern: '', file: 'https://github.com/sayalee2326/my-app.git', includePathPattern: '', metadatas: [''], redirectLocation: '', sseAlgorithm: '', tags: '', text: '', workingDir: ''
                 }   
             }
        }
    }
}
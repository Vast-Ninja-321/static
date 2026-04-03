pipeline {
    agent any

    stages {
        stage('Upload to AWS') {
            steps {
                script {
                    withAWS(region: 'us-east-1', credentials: 'jenkins') {
                        s3Upload(
                            bucket: 's3bucket-jenkins-project',
                            file: 'index.html'
                        )
                    }
                }
            }
        }
    }
}

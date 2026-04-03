pipeline {
    agent any

    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e index.html'
            }
        }

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

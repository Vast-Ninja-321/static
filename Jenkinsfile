pipeline {
    agent any

    stages {
        stage('Upload to AWS') {
            steps {
                script {
                    // Create the file
                    writeFile file: 'index.html', text: '''
<!DOCTYPE html>
<html>
<head>
  <title>Jenkins S3 Deploy</title>
</head>
<body>
  <h1>Hello from Jenkins + S3</h1>
</body>
</html>
'''

                    // Upload to S3
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

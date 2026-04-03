pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        sh 'echo "Hello World"'
                withAWS(region:'us-east-1',credentials:'jenkins') {
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'s3bucket-jenkins-project')
      }
    }

  }
}

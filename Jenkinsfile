pipeline {
  agent {
    docker { image 'node:16-alpine' }
  }
  stages {
    stage('Test') {
      steps {
        sh '''
        node --version
        ls -la
        pwd
        cat /var/lib/jenkins/workspace/TestProject2/helloWorld/deploy.yaml
        '''
      }
    }
  }
}

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
        cat helloWorld/deploy.yaml
        '''
      }
    }
  }
}

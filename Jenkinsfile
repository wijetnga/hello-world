pipeline {
  agent {
    docker { image 'node:16-alpine' }
  }
  stages {
    stage('Checkout'){
           steps {
                url: 'https://github.com/wijetnga/hello-world',
                branch: 'main'
           }
    }  
    stage('Test') {
      steps {
        sh '''
        node --version
        ls
        '''
      }
    }
  }
}

pipeline {
  agent { dockerfile true }
  stages {
    stage('Test') {
      steps {
        sh '''
          node --version
          git --version
          curl --version
        '''
      }
    }
    stage('Test2') {
                echo 'Hello World'
                git branch: 'main', credentialsId: '4babe339-b976-47ad-a350-faeec6c6d1f0', url: 'https://github.com/wijetnga/hello-world'       
    }    
  }
}

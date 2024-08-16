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
        cat helloWorld/configMap.yaml
        sed -i -e 's/Morning/Afternoon/g' helloWorld/configMap.yaml
        cat configMap.yaml
        git add configMap.yaml
        git commit -m 'Updated the deploy yaml | Jenkins Pipeline'
        git push https://github.com/wijetnga/hello-world HEAD:main
        '''
      }
    }
  }
}

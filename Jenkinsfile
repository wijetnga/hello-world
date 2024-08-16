pipeline {
  agent any 
//{
//    docker { image 'alpine/git' }
//  }
  stages {
    stage('Test') {
      steps {
        script{ 
          sh '''
 #         git config --global user.name "${GIT_USERNAME}"
 #         git config --global user.password "${GIT_PASSWORD}"
          git config --global user.name "dzou"
          git config --global user.email "dzou@company.com"
 #         node --version
          ls -la
          pwd
          cat helloWorld/configMap.yaml
          sed -i -e 's/Morning/Afternoon/g' helloWorld/configMap.yaml
          cat helloWorld/configMap.yaml
          git add helloWorld/configMap.yaml
          git commit --amend --reset-author
          git commit -m 'Updated the deploy yaml | Jenkins Pipeline'
          git push https://github.com/wijetnga/hello-world HEAD:main
          '''
       
      }
    }
  }
 }
}

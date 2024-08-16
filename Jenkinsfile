pipeline {
  agent any 
//{
//    docker { image 'alpine/git' }
//  }
  stages {
    stage('Test') {
      steps {
        script{ 
          withCredentials([usernamePassword(credentialsId: '500c80a5-1066-4ad1-b5cc-ca025575ee56', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
          sh '''
          git config --global user.name "${GIT_USERNAME}"
          git config --global user.password "${GIT_PASSWORD}"
 #         node --version
          ls -la
          pwd
          cat helloWorld/configMap.yaml
          sed -i -e 's/Morning/Afternoon/g' helloWorld/configMap.yaml
          cat helloWorld/configMap.yaml
          git add helloWorld/configMap.yaml
          git commit -m 'Updated the deploy yaml | Jenkins Pipeline'
          git push https://github.com/wijetnga/hello-world HEAD:main
          '''
       }
      }
    }
  }
 }
}

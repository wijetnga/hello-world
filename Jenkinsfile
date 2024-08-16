pipeline {
    agent any 
    stages {
        stage('Checkout'){
            steps {
                git credentialsId: '8cd4aefc-fb60-4fec-857c-81042b2e4da6',  
                url: 'https://github.com/wijetnga/hello-world.git',
                branch: 'main'
            }
        }        
        stage('Build') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: '8cd4aefc-fb60-4fec-857c-81042b2e4da6', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                        // The credentials are available as environment variables USERNAME and PASSWORD
                        sh '''
                        echo "Using credentials $USERNAME and $PASSWORD"
                        ls -la
                        pwd
                        cat helloWorld/configMap.yaml
                        sed -i -e 's/Morning/Afternoon/g' helloWorld/configMap.yaml
                        cat helloWorld/configMap.yaml
                        git add helloWorld/configMap.yaml
                        git commit -m 'Updated the deploy yaml | Jenkins Pipeline'
                        git remote -v
                        git push origin
                        '''
                    }
                }
            }
        }
    
    }


}

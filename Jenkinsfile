properties([pipelineTriggers([githubPush()])])
 
pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        stage('Checkout SCM') {
            steps {
                checkout(
                    [
                        $class: 'GitSCM', 
                        branches: [[name: '*/master']], 
                        extensions: [], 
                        userRemoteConfigs: [[
                            credentialsId: '403c6e06-a112-4747-bcbd-c4af2d8a46ea', 
                            url: 'https://github.com/kshenk1/basic-jenkins-pipeline'
                            ]]
                    ]
                )
            }
        }
         stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}
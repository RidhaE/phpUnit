pipeline {
  agent any
    
 
    
  stages {
    
    stage('Initialize') {
        steps {
            //enable remote triggers
            script {
                properties([pipelineTriggers([pollSCM('* * * * *')])])
            }
        }
    }
        
 
     
    stage('Test') {
      steps {
         sh 'vendor/bin/phpunit'
      }
    }      
 
            stage ('Upload') {
            steps {
                rtUpload (
                    serverId: "Artifactory", // Obtain an Artifactory server instance, defined in Jenkins --> Manage:
                    spec: """{
                            "files": [
                                    {
                                        "pattern": "archive.zip",
                                        "target": "example-repo-local",
                                        "props": "p1=v1;p2=v2"
                                    }
                                ]
                            }"""
                )
            }
        }
  }
}

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
 
        
  }
}

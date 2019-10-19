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

     stage('install dependicies') {
        steps {
            bat 'composer install'
        }
    }
        
 
     
    stage('Test') {
      steps {
         bat 'vendor/bin/phpunit'
      }
    }      
 
        
  }
}

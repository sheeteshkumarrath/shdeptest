#!/usr/bin/env groovy
pipeline{
    agent{
        docker {
            //Run the Docker image and create Docker Container to perform the Pipeline activities
            image 'ubuntu'
            args '-u sheeteshubuntu'
                }
          }    
    stages{
    stage('Build') {      
        steps {
                echo 'Building...'
                 sh 'apt-get update'
                 sh 'apt-get inatall -y ssh'
                 sh 'apt-get install -y git'
                 sh 'apt-get install sudo'
                 sh 'chmod 700 Devnew.pem'    
                 sh 'chmod +x ./script/deploy'
              }
                    }

stage('Deploy Licious Web') { 
        steps { 
            echo 'Deploy Demo of Licious Dev Website..'           
        //Run the executable Deploy file            
            sh './script/deploy'
            echo 'Here, we are not actually deploying, just showing the branches under "Liciousweb" repo'          
               }
                   }
    }}

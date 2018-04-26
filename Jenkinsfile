#!/usr/bin/bash
pipeline{ 
   // stage('Image Load'){ def loadimage() { 
     //   sh'''
        //#!/bin/bash
        //docker load -i webdeploy.sheetesh.tar '''
    //}}
    
    agent{ 
        docker {
            //Run the Docker image and create Docker Container to perform the Pipeline activities
            sh'''
        #!/bin/bash
        docker load -i webdeploy.sheetesh.tar
        docker run -it webdeploy:sheetesh'''
          //  image 'webdeploy:sheetesh'
            args '-u root'
                }
          }    
    stages{
    stage('Build') {      
        steps {
                echo 'Building...'
                 //sh 'apt-get update'
                 //sh 'Yes y | apt-get inatall ssh'
                 //sh 'apt-get install -y git'
                 //sh 'apt-get install sudo'
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

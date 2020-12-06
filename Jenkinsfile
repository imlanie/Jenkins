#!/bin/bash
pipeline {
    agent any 
        stages {
                stage('Deploy to NP3') 
            
                    {
                   
                         environment { 
                                SSH_CREDS = credentials('/c/Users/Elaine/Downloads/myExamPrepKP.ppk')
                                }
                        
                       steps {
                //sh 'echo "SSH private key is located at $SSH_CREDS"'
                sh 'echo "SSH user is $SSH_CREDS_USR"'
                sh 'echo "SSH passphrase is $SSH_CREDS_PSW"'
                           echo 'successfully deployed to NP3'
            } 
                        
                        //steps {
                    //sh 'python --version'
                    //echo 'successfully deployed to NP3'
                       // }
                    }
            
                stage('Deploy to QA') 
                        {
                        steps {
                        //sh 'python --version'
                        echo 'successfully deployed to QA'
                            }
                        }
               
        
            //end stages
            }
    
            post { 
                always { 
                    echo 'Pipeline completed successfully.'
                }
            }
            //end post
        
    //end pipeline
    }


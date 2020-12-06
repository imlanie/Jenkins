#!/bin/bash
pipeline {
    agent any 
    
           parameters
                {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
        stages {
                stage('Deploy to NP3') 
            
                    {
                        
                        when {
                            branch 'test'
                        }
                   
                         environment { 
                                SSH_CREDS = credentials('myExamPrepPPK') // ssh username with private key
                          
                                       //AN_ACCESS_KEY = credentials('my-predefined-secret-text') 
                                       //SERVICE_CREDS = credentials('jenkins')  //Example Username/Password
                                }
                        
                       steps {
                //sh 'echo "SSH private key is located at $SSH_CREDS"'
                //sh 'echo "SSH user is $SSH_CREDS_USR"'
                //sh 'echo "SSH passphrase is $SSH_CREDS_PSW"'
                           echo 'successfully deployed to NP3'
                           echo "Hello ${params.PERSON}"
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


#!/bin/bash
pipeline {
    agent any 
    
           parameters
                {
                    string(name: 'CHG_NUMBER', defaultValue: 'CHG', description: 'Enter Change Ticket Number:')
                }
        stages {
                stage('Deploy to NP3') 
            
                    {
                        
                        when {
                            branch 'NP3'
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
                
            } 
                        
                        //steps {
                    //sh 'python --version'
                    //echo 'successfully deployed to NP3'
                       // }
                    }
            
                stage('Deploy to Prod') 
                        {
                            
                            when {
                            branch 'main'
                        }
                            
                        steps {
                        //sh 'python --version'
                        echo 'successfully deployed to Prod'
                        echo "Change Number:  ${params.CHG_NUMBER}"
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


#!/bin/bash
pipeline {
    agent any 
        stages {
                stage('Deploy to NP3') 
            
                    {
                   
                         environment { 
                                SSH_CREDS = credentials('myExamPrepPPK')
                                }
                        
                        
                        
                        steps {
                    //sh 'python --version'
                    echo 'successfully deployed to NP3'
                        }
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


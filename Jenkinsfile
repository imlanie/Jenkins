#!/bin/bash
pipeline {
    agent any 
        stages {
                stage('Deploy to NP3') 
            
                    {
                   
                         environment { 
                                AN_ACCESS_KEY = credentials('ec2-user') 
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


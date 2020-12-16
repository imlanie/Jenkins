#!/bin/bash
pipeline {
    agent any 
    
           parameters
                {
                    string(name: 'CHG_NUMBER', defaultValue: 'CHG', description: 'Enter Change Ticket Number:')
                }
                
        stages {
            stage('Deploy to NP3') {
            
                   environment { 
                                SSH_CREDS = credentials('myExamPrepPPK') // ssh username with private key
                                   //AN_ACCESS_KEY = credentials('my-predefined-secret-text') 
                                   //SERVICE_CREDS = credentials('jenkins')  //Example Username/Password
                                }
                        
                   steps {
                                   
                           //scp filetocopy.txt z_lnd_etl_svc@np3lndnjsvr01v:/opt/lending/etl/
                           //scp -r /workspace/directorypath z_lnd_etl_svc@np3lndnjsvr01v:/opt/lending/etl/  // to copy a whole directory instead 
                             echo 'this is where the file transfer will take place from the jenkins workspace to the NP3 server' 
                       
                       pscp -v -i c:\Users\Elaine\Downloads\NorCalDecember.ppk index.html ec2-user@ec2-13-52-230-121.us-west-1.compute.amazonaws.com:/var/www/html/index.html
                           //sh 'echo "SSH private key is located at $SSH_CREDS"'
                              
                           //sh 'echo "SSH user is $SSH_CREDS_USR"'
                             //sh 'echo "SSH passphrase is $SSH_CREDS_PSW"'
                           echo "${SSH_CREDS}"
                           
                            echo "${SSH_CREDS_USR}"
                           
                           echo 'Successfully deployed to NP3'
                
                        } // end steps 
                        
                        
                    }
            
                stage('Deploy to Prod') 
                        {
                            
                          // ensure that branch is main
                        //    when {
                        //  branch 'main'
                       // }
                            
                        steps {
                        
                           // echo "${branch.name}"
                           // sh 'python --version'
                        echo 'Successfully deployed to Prod'
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


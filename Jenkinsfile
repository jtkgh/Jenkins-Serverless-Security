pipeline {
      agent any
      
      
     
     stages {
          
         stage('Clone Github repository') {
            
           steps {
              
             checkout scm
           
             }
  
          }
           
      
       
         stage('CloudGuard Proact Code and Compliance Scan') {
       
            
            steps {
                  
                sh 'sudo npm install -g https://artifactory.app.protego.io/cloudguard-serverless-plugin.tgz'
              
                withAWS(credentials: 'CGW', region: 'us-east-1'){
                    
         
             
                
                sh 'cloudguard proact -m template.yaml '
                   
                        }
                     

               }
           
          }
    } 
}

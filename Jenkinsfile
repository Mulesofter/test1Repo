pipeline { 
     agent any 
         stages { 
             stage('Build') { 
                 steps { 
                     echo 'Application is in Building Phase' 
                     bat 'mvn clean install' 
                     } 
                 } 
             stage('Test') { 
                 steps { 
                     echo 'Application is in Testing Phase' 
                     bat 'mvn test' 
                       } 
                 } 
                 stage('Deploy to Cloudhub') {  
                   environment { 
                               ANYPOINT_CREDENTIALS = credentials('anypoint-platform') 
                               } 
                   steps { 
                            bat 'mvn deploy -DmuleDeploy -DmuleVersion=4.8.0 -Dusername=Peacelover79 -Dpassword=Malak2013# -DworkerType=Micro -Dworkers=1' 
                         } 
                    } 
         } 
     }

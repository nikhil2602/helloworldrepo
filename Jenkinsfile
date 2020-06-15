@Library('pipeline-library-demo')_
//def job_name=env.JOB_NAME;
//def build_number=env.BUILD_NUMBER;
def build_status="SUCCESS";

pipeline {
    agent any
    stages {
    stage('CheckOut'){
      steps{
        git 'https://github.com/nikhil2602/helloworldrepo.git'
        sayHello 'Working'
        //build_status="Checkout_Success";
        //slackNotification (job_name,build_number,build_status,env.STAGE_NAME)
        slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status,env.STAGE_NAME)
        
      }
    }
     /*stage('Clean WorkSpace'){
        steps{
            
            
                
                 bat "mvn clean package -f ./helloworld1 -DoracleHome=C:/Oracle/Middleware/Oracle_Home"
            
             //slackSend (color: '#FFFF00', message: "COMPLETED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' SUCCESS")
            //slackNotification
           
        }
    }*/
    /*stage('upload') {
           steps {
              script { 
                 def server = Artifactory.server 'jenkins-artifactory-server'
                 def uploadSpec = """{
                    "files": [{
                       "pattern": "C:\\Users\\Vikram\\.jenkins\\jobs\\artifactory_test\\workspace\\helloworld1\\.data\\maven\\sbconfig.sbar",
                       "target": "helloworld_repo"
                    }]
                 }"""

                 server.upload(uploadSpec) 
               }
            }
    }
    stage('download') {
           steps {
              script { 
                 def server = Artifactory.server 'jenkins-artifactory-server'
                 def downloadSpec = """{
                    "files": [{
                       "pattern": "helloworld_repo/sbconfig.sbar",
                       "target": "C:\\Users\\Vikram\\.jenkins\\jobs\\artifactory_test\\workspace\\download_artifact\\sbconfig.sbar"
                    }]
                 }"""

                 server.download(downloadSpec) 
               }
            }
    }*/
    /*stage('Deploy') {
      steps {
        bat "mvn pre-integration-test -f ./helloworld1 -DoracleServerUrl=http://localhost:7101/  -DoracleUsername=weblogic -DoraclePassword=welcome1 -DoracleHome=C:/Oracle/Middleware/Oracle_Home"
         }
      }*/
      
    }
}

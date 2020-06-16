@Library('pipeline-library-demo')_

def build_status1="SUCCESS";
def build_status2="FAILURE";
def url = clone_url;
pipeline {
    agent any
    stages {
    stage('CheckOut'){
      steps{
        script {
		try {
			//git 'https://github.com/nikhil2602/helloworldrepo.git'
			
            		//echo 'ref details  ' + ref
			echo 'repo url ' + ${url}
			
			slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status1,env.STAGE_NAME)
		}
		catch (Exception e) {
			//println("exception occured");
			slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status2,env.STAGE_NAME)
			
		}
        }
      }
    }
    /* stage('Clean WorkSpace'){
        steps{
            script {
			try {
				bat "mvn clean package -f ./helloworld1 -DoracleHome=C:/Oracle/Middleware/Oracle_Home"
				slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status1,env.STAGE_NAME)
			}
			catch (Exception e) {
				//println("exception occured");
				slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status2,env.STAGE_NAME)
			}
			}
        }
    }
    stage('upload') {
           steps {
              script {
				try {
                 def server = Artifactory.server 'jenkins-artifactory-server'
                 def uploadSpec = """{
                    "files": [{
                       "pattern": "C:\\Users\\Vikram\\.jenkins\\jobs\\artifactory_test\\workspace\\helloworld1\\.data\\maven\\sbconfig.sbar",
                       "target": "helloworld_repo"
                    }]
                 }"""
                
                 server.upload(uploadSpec) 
                 slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status1,env.STAGE_NAME)
				}
				catch (Exception e) {
				//println("exception occured");
				slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status2,env.STAGE_NAME)
				}
               }
            }
    }
    stage('download') {
           steps {
              script {
				try{
                 def server = Artifactory.server 'jenkins-artifactory-server'
                 def downloadSpec = """{
                    "files": [{
                       "pattern": "helloworld_repo/sbconfig.sbar",
                       "target": "C:\\Users\\Vikram\\.jenkins\\jobs\\artifactory_test\\workspace\\download_artifact\\sbconfig.sbar"
                    }]
                 }"""
                
                 server.download(downloadSpec)
				 slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status1,env.STAGE_NAME)
                  
              }
			catch (Exception e) {
				//println("exception occured");
				slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status2,env.STAGE_NAME)
			}	
               }
            }
    }
    stage('Deploy') {
      steps {
		script {
		try {
			bat "mvn pre-integration-test -f ./helloworld1 -DoracleServerUrl=http://localhost:7101/  -DoracleUsername=weblogic -DoraclePassword=welcome1 -DoracleHome=C:/Oracle/Middleware/Oracle_Home"
            slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status1,env.STAGE_NAME)
		    
		}
		 catch (Exception e) {
				//println("exception occured");
				slackNotification (env.JOB_NAME,env.BUILD_NUMBER,build_status2,env.STAGE_NAME)
			}
		 }
	  }
      }*/
      
    }
    /*post {
        always {
            mail bcc: '', body: 'Hello World', cc: '', from: '', replyTo: '', subject: 'Test', to: 'gnikhilyadav26@gmail.com'
        }
    }*/
}


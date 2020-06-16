@Library('pipeline-library-demo')_
def var1="osb";
//def build_status1="SUCCESS";
//def build_status2="FAILURE";
//def url = clone_url;
pipeline {
    agent any
    stages {
	    stage('check') {
		    steps {
			    script {
				    if(var1=="osb"){
					    println("if exe");
				    	osbproject()
				    }
				    else {
					println("else exe");   
				    }
			    }    
		    }
	    }
    /*stage('CheckOut'){
	    
      steps{
        script {
		try {
			git clone_url    //'https://github.com/nikhil2602/helloworldrepo.git'
			
            		//echo 'ref details  ' + ref
			//echo 'repo url ' + url
			
			slackNotification.status1 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
		}
		catch (Exception e) {
			//println("exception occured");
			slackNotification.status2 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
			
		}
        }
      }
    }*/
	    
	    
    /* stage('Clean WorkSpace'){
        steps{
            script {
			try {
				bat "mvn clean package -f ./helloworld1 -DoracleHome=${oracleHome}"
				slackNotification.status1 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
			}
			catch (Exception e) {
				//println("exception occured");
				slackNotification.status2 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
			}
			}
        }
    }*/
	    
    /*stage('upload') {
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
                 slackNotification.status1 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
				}
				catch (Exception e) {
				//println("exception occured");
				slackNotification.status2 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
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
				 slackNotification.status1 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
                  
              }
			catch (Exception e) {
				//println("exception occured");
				slackNotification.status2 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
			}	
               }
            }
    }
    stage('Deploy') {
      steps {
		script {
		try {
			bat "mvn pre-integration-test -f ./helloworld1 -DoracleServerUrl=${oracleServerUrl}  -DoracleUsername=${oracleUsername} -DoraclePassword=${oraclePassword} -DoracleHome=${oracleHome}"
            slackNotification.status1 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
		    
		}
		 catch (Exception e) {
				//println("exception occured");
				slackNotification.status2 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
			}
		 }
	  }
      }*/
      
    }
    /*post {
        always {
            mail bcc: '', body: 'Consolidated OSB', cc: '', from: '', replyTo: '', subject: 'Test', to: 'gnikhilyadav26@gmail.com'
        }
    }*/
}


@Library('pipeline-library-demo')_
def repo_name=name;
//def build_status1="SUCCESS";
//def build_status2="FAILURE";

pipeline {
    agent any
    stages {
	  stage('checking_condition') {
             steps {
                script {
                if(repo_name=="helloworldrepo")
                {
                    stage('CheckOut'){
	    
      //steps{
			    echo "inside chceckout"
        script {
		try {
			git clone_url    //'https://github.com/nikhil2602/helloworldrepo.git'
			slackNotification.status1 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
		}
		catch (Exception e) {
			//println("exception occured");
			slackNotification.status2 (env.JOB_NAME,env.BUILD_NUMBER,env.STAGE_NAME)
			
		}
        }
	//}
    }
		stage('Clean WorkSpace'){
        
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
		stage('Deploy') {
      
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
                }
                else
                {
                 stage('else stage') {
                       echo "else stage1"
                    }
                 }
               }
             }
           }
//----------------------------------------
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


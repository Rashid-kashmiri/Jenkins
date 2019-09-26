pipeline {
	
 agent any
	
stages {
	stage ('Checkout Code'){
		steps {		
		     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/DevOpsClassCodes.git']]])
		       }
		     }
	stage ('BuildIn){
		steps {				
			sh 'mvn clean compile'
			sh 'mvn test'
			sh "mvn package"
			/target/addressbook.war
		}		
	}
	
	stage('BuildDonetoartifacts'){
            steps {
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
    }
}   
	  	
	


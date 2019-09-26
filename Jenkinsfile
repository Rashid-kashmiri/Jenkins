pipeline {
	
 agent any
	
stages {
	stage ('Checkout Code'){
		steps {		
		     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/DevOpsClassCodes.git']]])
		       }
		     }
	stage ('BuildIn'){
		steps {				
			sh 'mvn clean compile'
			sh 'mvn test'
			sh "mvn package"			
		}		
	}
	
	stage('ArchiveArtifacts'){
            steps {                
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true , onlyIfSuccessful: true
            }
        }
    }
}   
	  	
	


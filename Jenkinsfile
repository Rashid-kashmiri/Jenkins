pipeline {
	
 agent any
	
stages {
	stage ('Checkout Code'){
		steps {		
		     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/mvnrepo.git']]])
		       }
		     }
	stage ('Build'){
		steps {				
			sh 'mvn clean compile'
			sh 'mvn test'
			sh "mvn package"			
			}		
		}
	   }   
	  }	
	


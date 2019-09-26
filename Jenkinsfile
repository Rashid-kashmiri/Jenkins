pipeline {
	
 agent any
	
stages {
	    stage ('Checkout Code'){
	     steps {
		 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/nvnshoppingcart.git']]])
	     }
		}

	     stage ('***COMPILE THE CODE***'){
		steps {
		sh 'mvn clean compile'
		}
	      }

	     stage ('***First TEST THE CODE***'){
		steps{
		sh 'mvn test'	
		}
	      }

	     stage ('***PACKAGE THE CODE***'){
		steps{
		sh "mvn package"
		}	
	     }

	     stage ('***Deploy to Nexus***'){
		//sh 'rm /var/lib/tomcat/webapps/nvnshoppingcart*'
	      steps{
		sh 'sudo cp **/*.war /opt/Jenkins/'	
		}	       
	      }	   
	  }		
	}


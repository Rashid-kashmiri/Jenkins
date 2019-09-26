pipeline {
	
agent any
options { timestamps () }
		
stages {	
	stage ('Checkout Code'){	
		steps {	
		     
		     checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/Rashid-kashmiri/DevOpsClassCodes.git']]])
		       }
		     }
	stage ('Compile'){		
		steps {				
			sh 'mvn clean compile'								
		}			
	}
	 stage('Test') {
            steps {
                /* `make check` returns non-zero on test failures,
                * using `true` to allow the Pipeline to continue nonetheless
                */
		sh 'mvn test'		
                junit '**/target/*.xml' 
		sh 'mvn package'
            }
        }
	
	stage('ArchiveArtifacts'){
            steps {                
                archiveArtifacts artifacts: '**/target/*.war', fingerprint: true , onlyIfSuccessful: true		   
            }
        }
    }
}   
	  	
	

